---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "What Is Machine Learning"
subtitle: "A definition by blocks"
summary: "In this post, I look at the different parts of a typical machine learning problem."
authors: [geoff]
tags: [machine learning, tutorial]
categories: [tutorial]
date: 2017-11-02T02:34:31+02:00
lastmod: 2020-04-21T22:08:31+02:00
featured: true
commentable: true
draft: false
share: true
toc: true  # shows table of contents

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

Hi everyone, welcome back. Tonight I was having dinner with some engineer friends (sadly not a plat en sauce) and the subject of Machine Learning popped up.

The discussion quickly almost turned religious, between believers and non believers, those that thought it's over hyped, those who just use it as a tool and those who research it like myself. All in all, it made me feel that even engineers have a very vague sense of what exactly is Machine Learning. I've noticed people in general often mix it up with other concepts that either include it such as AI or that it includes such as the Supervised Learning paradigm. Since it's been a long time that I've been wanting to address this issue, here I go.

The aim of this article is to explain ML assuming that you already have some general mathematical background, and have (very) basic knowledge of optimization i.e. you know what argmin is. I also assume that you can read equations. 

My definition of Machine Learning is the following:

> Choosing a task and learning a statistical model from data that will perform well on this task.

This definition seems extremely vague, so I'll explain each part in more detail. I'm intentionally leaving out complications due to taking into account randomness in the data. Of course we need this both in theory and in practice.

# Choosing a task

Examples of tasks are recognizing handwritten digits, translating sentences from a language to another, identifying people in pictures, forecasting the weather or stock prices, grasping an object with a robot arm... Basically any clear-cut problem is a task. This part doesn't suppose an actual mathematical expression of the task. On the other hand, it does require to be very precise as we'll see in the following example.

# A model that will _perform well_

To define what perform well means, you often want to define a loss or cost function for your task, that given your data and model, i.e. the specific function of your data you're considering, outputs a measure of its performance. A simple example: suppose my (very basic) task is to always output the number 0. A good metric could be the distance of my function output to 0. Then it's obvious that if f and g are the constant functions respectively equal to 42 and 0.2, g performs better on this task than f, for every distance function other than the 0-1 distance. All these different distance functions yield a different metric for the same task.
The problem is then to minimize your loss function over the class of functions that you will choose in the next step.

# A statistical model

Choosing a class of functions that take as inputs the data you want to use for the task, i.e. often a high-dimensional vector, and outputs a real number or another vector. A class of functions is a group of functions that share a certain structure, with different parameters. An example of this is the class of linear functions that can be written : $f(X) = Xw + b $, where vectors $w$ and scalar $b$ are the parameters.

# Learning the model

This here is the actual way that you will choose your function that minimizes your loss over your data in the class of functions that you chose. This is the learning and what makes ML so compelling to me, and makes it treated as almost magical in the media. It is usually done by optimizing the loss function, either in a principled or heuristic way. Optimization is the field of studying how to find minima of loss functions (sometimes under constraints).

This is also what made the success of deep learning, where in the parameter space, the overall loss is differentiable with regard to the parameters, allowing us to simply glide towards a (near) optimal solution using Stochastic Gradient Descent.

# Who does what?

ML to me is described by these 4 steps. Both researchers and engineers usually focus on a subset of these steps. For example, for a well-known task such as classification (i.e. for each data point, outputting the category it should belong to), or regression (for each data point, predicting the value of something), both the task and the loss function are well known. Most work can then focus on choosing the model family and how to compute the best model of the family. On the other hand, for unsupervised learning tasks, the task is not as clear, and the loss is an open question. On their side, ML engineers will often have a hard time modelling their domain-specific task in a nice loss function, and then apply known model families and optimization schemes.

# Now for an example

Let's consider the task (step 1) of recognizing hand written digits, supposing that we know the ground truth for a subset of our data -- we'll call this subset our training set. Our input is going to be a 784 (ie. 28x28)-vector representing an image. Each of its dimensions corresponds to a pixel in the image. Here is a sample image for a 1.


{{< figure src="MNIST-Matrix.png" title="Sample image and matrix representation. From old Tensorflow tutorials. Dimensions are incorrect." lightbox="true" >}}

Now that we identified our task, we want to model it using a loss function (step 2). We want our output to tell us if the sample is a 0, 1, 2... or 9. An intuitive way to represent this is to have a 0-1 error function : if we predict the correct label, our loss is 0 and 1 if we make a mistake. Machine Learners rarely use this in practice because the discrete nature of this loss make the 4th step, the learning, harder.

A common and smart way to represent a very similar task is to have our function output a vector of probabilities over the 10 classes, i.e. a positive vector of size 10, with coordinates that sum to 1. Our new proxy task is predicting how likely a sample is to belong to a certain class, given labelled training data. We'll call this vector $ \hat{y}$ as opposed to $ y$ which is the correct probability distribution, where $ y_i = 1$ if and only if $ i$ is the correct class of our data point. We need a metric to tell if $ \hat{y}$ is far from $ y$. Cross entropy is the go-to method for this. Its expression for each data sample is:

$$ L(\hat{y}, y) = -\sum_i y_i \log(\hat{y_i})$$

Note that if we did not know the $y_i$, it would be a different task, and would thus require a different loss function.

In practice, we'll minimize the empirical average of this loss over our training data.

At this point, we want to find our model class, i.e. the structure in our functions $f$. An easy example is using a one-hidden-layer neural network, with a sigmoid activation function $\sigma$. $f$ can be written as:

$$ f(x) = \sigma ( X W_0+ b_0)w_1 + b_1$$

So our model is the set of functions that can be written this way, for any weights $W_0, w_1, b_0, b_1$.

Finally comes the learning. We want to learn what function of our class minimizes our loss. This is equivalent to finding the weights that minimize our loss, given the preceding structure. Mathematically, our minimization problem is:

$$\min_{W_0, w_1, b_0, b_1} - \sum_{i,j} y_i \log(\sigma (X_jW_0 + b_0)w_1  + b_1)$$

where the sum over $i$ refers to the different classes $(0, 1,...9)$ in our problem and the sum over $j$ refers to the different samples in our training set.

NB for you who are familiar with optimization: This problem is somewhat nice, because the loss function is differentiable with respect to the weights, although it is not convex in the weights. This explains why people use Stochastic Gradient Descent, an algorithm that guarantees us to find a local minimum of our loss and the corresponding weights.

Once we find the optimal weights, we have our candidate, and have finished our learning! For this particular digit recognition dataset, common classification error runs around 5% on a validation set. The classification error used here is the intuitive 0-1 loss that we defined earlier.

A validation set is a set similar to the training set, meaning that we also know the correct labels $y_i$. The difference with the training set is that we never fed it to the learning algorithm. This means our model's parameters were not optimized for outputting correct results for the validation set. The hope is that the parameters we learned generalize enough to work well on the validation set. We want this so that we are confident our model will perform well on any new data we feed to it, assuming this data was generated in the same manner as the training data. More on this in a future post.

# Conclusion

I went over what makes a problem a Machine Learning problem: the 4 phases of Choosing a Task, Modelling the Task, Choosing a Model Class, and Learning i.e. Optimizing over the Model Class. I hope the example helped to clear this up. We also saw that by trying to solve a specific task, we may have to define a new task that is a good proxy for our original task. In the end though, we always validate our approach on the first task on held-out data, using the loss function that we designed for it, here the 0-1 error loss.

I hope this helps making Machine Learning less of a buzz word and more understandable! I'm looking forward to your comments, don't hesitate to leave one below.

## Going further

The Bible of ML: 
Hastie, T.; Tibshirani, R. & Friedman, J. (2001), The Elements of Statistical Learning , Springer New York Inc. , New York, NY, USA .

The Bible of Optimization, basic and advanced:
Boyd, S.; and Vandenberghe, L. (2004), Convex Optimization. Cambridge University Press, New York, NY, USA.

The Bible of Deep Learning:
Goodfellow, I.; Bengio Y.; and Courville, A. (2016), Deep Learning. MIT Press



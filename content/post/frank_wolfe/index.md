---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Stochastic Frank-Wolfe"
subtitle: "How finite sums and duality theory allow us to design a state-of-the-art stochastic Frank-Wolfe algorithm."
summary: ""
authors: [admin]
tags: [Frank-Wolfe]
categories: [optimization]
date: 2020-04-29T16:18:11+02:00
lastmod: 2020-04-29T16:18:11+02:00
featured: true
draft: true

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
projects: [frank-wolfe]
---

In this post, we focus on designing a stochastic variant of the Frank-Wolfe (FW) algorithm. Details can be found in our paper[^1]. We'll start with a brief recap on what the Frank-Wolfe algorithm is, and why we would prefer it over another constrained optimization algorithm like Projected Gradient descent (PGD). Then, we'll see why the basic version of FW isn't friendly with the stochastic settings that often appear in machine learning settings.

# What is the Frank-Wolfe algorithm?

The Frank-Wolfe algorithm is a **constrained optimization algorithm**. It aims to solve problems of the form:

$$\min_{\bf{w}\in \mathcal C} f(\bf w),$$

where $f$ is our \`objective' function, and $\mathcal C$ is our constraint set. In the machine learning setting, $w$ is the vector of parameters of our model, and $f$ implicitly depends on our data. We assume that we can compute $\nabla f(\bf w)$, the gradient of our objective function, for a given vector of parameters $\bf w$.


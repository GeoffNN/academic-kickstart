---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Frank-Wolfe"
summary: "Making Frank-Wolfe algorithms practical and scalable."
authors: [geoff]
tags: [Optimization]
categories: [Machine learning]
date: 2020-04-21T21:58:14+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

The Frank-Wolfe (FW) or Conditional Gradient algorithm is a family of first-order algorithms for constrained optimization. They seek to solve problems of the form:

$$\min_{x\in \mathcal{C}} f(x), $$

where $\mathcal{C}$ is a non-empty convex and compact set, and the objective function $f$ is differentiable, and often smooth. The gist is the following:

 - Given a current iterate $x_t$,
 - Minimize the linear approximation (i.e. the $1^\text{st}$ order Taylor expansion) of $f$ over $\mathcal C$ ; this minimum is attained on $s_t$, an extremal point of $\mathcal C$;
 - Update the iterate as a convex combination: $x_{t+1} = x_t + \gamma_t (s_t - x_t)$ for a given step-size $\gamma_t$.


It has many variants with different advantages, which can often be combined.  My work has focused on two specific problems:
 - Designing an (almost) hyper-parameter free adaptive step-size scheme, i.e. choosing $\gamma_t$.
 - Designing a batch-wise stochastic variant of the algorithm, reducing overall complexity of the algorithm.

---
title: "Linearly Convergent Frank-Wolfe with Backtracking Line-Search"
date: 2018-06-13
publishDate: 2020-01-14T03:12:12.973981Z
authors: ["Fabian Pedregosa", "geoff", "Armin Askari", "Martin Jaggi"]
publication_types: ["1"]
abstract: "Structured constraints in Machine Learning have recently brought the Frank-Wolfe (FW) family of algorithms back in the spotlight. While the classical FW algorithm has poor local convergence properties, the Away-steps and Pairwise FW variants have emerged as improved variants with faster convergence. However, these improved variants suffer from two practical limitations: they require at each iteration to solve a 1-dimensional minimization problem to set the step-size and also require the Frank-Wolfe linear subproblems to be solved exactly. In this paper, we propose variants of Away-steps and Pairwise FW that lift both restrictions simultaneously. The proposed methods set the step-size based on a sufficient decrease condition, and do not require prior knowledge of the objective. Furthermore, they inherit all the favorable convergence properties of the exact line-search version, including linear convergence for strongly convex functions over polytopes. Benchmarks on different machine learning problems illustrate large performance gains of the proposed variants."
featured: true
publication: "*AISTATS 2020*"
tags: [Frank-Wolfe, Optimization]
url_pdf: "http://arxiv.org/abs/1806.05123"
projects: [Frank-Wolfe]
---


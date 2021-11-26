---
title: "Stochastic Frank-Wolfe for Constrained Finite-Sum Minimization"
date: 2020-02-01
publishDate: 2020-04-14T03:12:12.973104Z
authors: [geoff, "Gideon Dresdner", "Alicia Tsai", "Laurent El Ghaoui", "Francesco Locatello", "Robert Freund", Fabian Pedregosa"]
publication_types: ["3"]
abstract: "We propose a novel Stochastic Frank-Wolfe (a.k.a. Conditional Gradient) algorithm with a fixed batch size tailored to the constrained optimization of a finite sum of smooth objectives. The design of our method hinges on a primal-dual interpretation of the Frank-Wolfe algorithm. Recent work to design stochastic variants of the Frank-Wolfe algorithm falls into two categories: algorithms with increasing batch size, and algorithms with a given, constant, batch size. The former have faster convergence rates but are impractical; the latter are practical but slower. The proposed method combines the advantages of both: it converges for unit batch size, and has faster theoretical worst-case rates than previous unit batch size algorithms. Our experiments also show faster empirical convergence than previous unit batch size methods for several tasks. Finally, we construct a stochastic estimator of the Frank-Wolfe gap. It allows us to bound the true Frank-Wolfe gap, which in the convex setting bounds the primal-dual gap in the convex case while in general is a measure of stationarity. Our gap estimator can therefore be used as a practical stopping criterion in all cases."
featured: true
publication: "*arXiv:2002.11860 [cs, math]*"
tags: [Frank-Wolfe, Optimization, Machine Learning]
url_pdf: "http://arxiv.org/abs/2002.11860"
projects: [Frank-Wolfe]
---


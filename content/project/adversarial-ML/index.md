---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Adversarial ML"
summary: ""
authors: [geoff]
tags: []
categories: []
draft: True
date: 2021-11-26T09:11:51-08:00

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

A few years ago, research CITE showed that modern deep learning models were brittle to adversarial attacks. Subsequent research CITE has shown that this poses a definite security threat for models deployed in the real world. It has then prompted research to fix this issue, typically by leveraging previously developped techniques from the field known as Robust Optimization. 

Interestingly, models trained to be robust are qualitatively different from models which are not. Their decision boundaries are different, and this can be leveraged to study data CITE generative model paper with robust models.
In the reverse, methods for generating adversarial attacks can be used for probing models, and performing sensitivity analysis on models. This projects aims to tackled the specific case of "backdoored" or "trojaned" models, and to develop tools for probing models for such weaknesses. 
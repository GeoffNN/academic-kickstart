---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: Linearly Convergent Frank-Wolfe without Prior Knowledge
event: "OPT2019"
event_url: "https://opt-ml.org/"
location: Vancouver, Canada
summary:
abstract: "Structured constraints in Machine Learning have recently brought the Frank-Wolfe (FW) family of algorithms back in the spotlight. Recently, the Away-steps (A) and Pairwise (P) FW variants have been shown to converge linearly for polytopic constraints. However, these improved variants suffer from two practical limitations: each iteration requires solving a 1-dimensional minimization problem to determine the step-size along with an exact solution to the Frank-Wolfe linear subproblems. In this paper, we propose simple modifications of AFW and PFW that lift both restrictions simultaneously.
Our method relies on a sufficient decrease condition to determine the step-size. It only requires evaluation and gradient oracles on the objective, along with an approximate solution to the FrankWolfe linear subproblems. Furthermore, the theoretical convergence rates of our methods match ones for the exact line-search versions. Benchmarks on different machine learning problems illustrate large practical performance gains of the proposed variants."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
# date: 2019-12-14T14:45
# date_end: 2019-12-14T15:00
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: 2019-12-14T14:45:00-07:00

authors: [geoff, Armin Askari, Fabian Pedregosa, Martin Jaggi]
tags: [Frank-Wolfe, Optimization]

# Is this a featured talk? (true/false)
featured: true

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

# Optional filename of your slides within your talk's folder or a URL.
url_slides:

url_code:
url_pdf:
url_video:

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [Frank-Wolfe]
---

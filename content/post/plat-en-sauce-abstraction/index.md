---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Plat en Sauce Abstraction"
subtitle: ""
summary: ""
authors: [geoff]
tags: [food, plat en sauce]
categories: [food]
date: 2017-05-30T01:10:08+02:00
lastmod: 2020-04-23T01:10:08+02:00
featured: false
draft: false

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

Hi all! Here is my first post on food! I hope you enjoy it and am looking forward to your comments! Today, I'll focus on the French Plat en sauce concept.

I found an old cooking book in one of my parents' shelves a few months ago and finally got around to checking it out and trying some things in it. The book is called Le Répertoire de la Cuisine (1914 for the first edition) by Théodore Gringoire and Louis Saulnier. The Répertoire is a major guide/recipe book for people who already know some technical French cuisine vocabulary - but nowadays, you can just Google them and find out all about what monder, singer or chemiser mean. I won't reproduce the recipe from the book here - you can probably find a PDF on internet or buy it on Amazon. I will add my own recipes in the following days, tune back in soon!

I moved to the US a few months ago,  and started missing the homey family French cuisine tastes. In my mind, nothing is more characteristic of this than a Blanquette and other plats en sauce : sauce entrées where meat and veggies are slowly cooked with herbs and wine.  I read and tried a few different recipes from the Répertoire inspired from Estouffade (traditionnelle and à la provençale) and Blanquette. 

My maths/CS background made me realize that these can all be abstracted to a generic Plat en sauce, which most of you experienced cooks probably already know. Couscous, Coq au vin, Bœuf bourguignon, Fricassée or even Curry implement this. They're all pretty cheap and healthy dishes, and the abstraction allows for creation and variation depending on your current tastes and desires. Here is what makes up a good plat en sauce in my mind, with the usual French interpretations of each category.

 - Meat: beef stew or equivalent for other animals such as veal or lamb.
 - Fonds:  stock - traditionally either white if made from poultry, veal or vegetables or brown if made from red meat
 - Wine: same color as the fonds, i.e. red for dark fonds and white for light fonds.
 - Vegetables: usually onions, carrots and mushrooms at least - any other root can do, e.g. parsnip for some tartness
 - Carbs: usually rice or steamed potatoes, the former being my favorite to have a donburi-style Plat en sauce where the rice gets soaked in the sauce.
 - Spices, herbs and various seasonings: bouquet garni (thyme, rosemary and sage) is the most frequent for French dishes, but Ras El-Hanout would be its couscous equivalent. I also consider the egg/heavy cream in Blanquette in this category.
 - Optional: a roux to make the sauce thicker.  Always add this at the very end.

> Onions have two uses in these recipes: sliced onions, usually in quarters, are for eating, and whole onions are spiked with cloves to flavor the broth and to facilitate removing the cloves in one go before serving the dish. This allows not to end up with a violent clove surprise while eating.

Roux: mix melted butter and flour (around half and half) and cook till the mixture is the color you want. Darker gives a more nutty taste, but doesn't thicken the sauce as much. Always mix with a few ladles of sauce first before pouring in the main pot to avoid lumps.

I'll progressively add my recipes for different implementations of Plat en sauce as soon as I've tweaked them well enough, come back soon for more! Check my Recipes page for the up to date version.

Let me know if this helped you make one of these dishes or if you tried deriving a new plat en sauce from the abstraction! Here are some ideas that I'd like to try:

 - a vegetarian one, using tofu and vegetable stock
 - using ichiban-dashi (kombu seaweed and fish stock) for an umami-tasting base

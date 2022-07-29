---
title: 'Custom layout'
date: 2022-07-29
permalink: /posts/2022/07/network-layout/
tags:
  - notes
  - resources
---
If you have been playing around with network aesthetics, you have probably spend some time trying to figure out **what layout works best to represent your data**. After all, network's sole purpose is to visually represent _many complex_ relationships in a meaningful and digestable way. So, this step should not be underestimated! Thankfully, igraph has several [layouts](https://r-graph-gallery.com/247-network-chart-layouts.html) you can use. 

Sometimes these might not be _exactly_ what you're looking for. No worries, you can create a customizable network layout! I'm going to walk you through how I created a custom layout! **Fair warning:** it is a bit cumbersome and not the most efficient code (alternatively, I would suggest using a forloop), but it works! Please proof and fully test all codes for your own use.

For this tutorial, I am building off of my [previous post](https://claireloconnell.github.io/posts/2022/07/networkaesthetics/), so check that out first! 

So, we are starting off with this network: 
![Screenshot (121)](https://user-images.githubusercontent.com/78130420/181688859-e62e1ca1-0be1-4255-96a9-c8762f4d0c96.png)

Not bad, but it could use some work! Some of the nodes are clumped together such that there is a decent amout of white space and the edges, especially the blue edges, are getting lost among the black. I can fix this if I organize the nodes by site to really emphasize the relationships across site. This way, vertices from the same site will be plotted in a circle in one of four quadrants of the plot. So here is my plan:

For each site,
1. Subset my edgelist by site captured 
2. Create network object 
3. Manipulate x,y coordinates 
4. Combine manipulated x,y coordinates into 1 df
5. Plot! 


First, I subset my edgelist to only include interaction data between actors and subjects of a particular site (Fig.1). I ran into trouble when I tried to create a network object with attributes, and I quickly realized that igraph struggles when the number and/or identity of the individuals listed in the edgelist does **not** match the attribute list. So, I filtered my attribute data as well. Once I had my network object, I used the `layout.circle()` function to get the coordinates. I converted the list into a dataframe, renamed the columns, and added what site these coordinates belonged to (this step is mostly to keep myself organized). Then 

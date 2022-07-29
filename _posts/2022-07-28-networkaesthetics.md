---
title: 'Network attributes and aesthetics'
date: 2022-07-28
permalink: /posts/2022/07/networkaesthetics/
tags:
  - notes
  - resources
---
**Here I describe some basic aesthetics, and I show you how I incorportate attributes to my networks. Huge shout out to Liz Hobson for showing me most of these tips!!**

Once you're comfortable going from a dataframe (whether it is an _edgelist_ or _adjacency matrix_) to a plot, it's time to start thinking about aethetics! In my opinion, this is the best and most frustrating part. It's fun because this is where your vision really comes together, and you can create a really beautiful network that is easy to interpret and visually appealing! However, it can be tricky forcing R to see your vision through. Thankfully, there are many packages and functions out there to help you out. You can use **igraph** or **ggraph** to plot networks. Which one you use somewhat depends on what you want to accomplish, but for this tutorial, I will be using igraph. 

If I were to run the line `igraph::plot(newtorkobject)`, igraph would output a very simple (but ugly) network. It would get the job done, but it would be difficult to interpret. Thankfully, igraph has _many_ arguements that allow us to specify different aesthetics including the layout, vertex and edge size, color, and shape. You can manipulate label text and orientation. All this to say that networks can and should be highly customizable for your data. 

**GOAL:** I am attempting to plot allopreening relationships among a group of 22 monk parakeets. Nodes correspond to birds, color represents the site they are from, shape represents sex. Edges represent allopreening relationship strength, so the stronger the relationship, the thicker the edge. In addition to my edgelist, I have a dataframe (df) called _atts_ that contains a list of all individuals, the site they were captured from, and sex. 

Make sure you have installed igraph before getting started!
<pre>
install.packages("igraph")
library(igraph)
</pre>
I also skipped some important pre-network steps, so if you're confused, go check out earlier tutorials! *This tutioral is for aesthetics only*
 
First, I convert my edgelist to a network object called _graph_ with the function `graph_from_data_frame()` (line 103). Here is where I tell R to reference my attributes dataframe. I do this with the arugement `vertices =`. Now, my network object contains actors, subjects, a count of their interactions, site captured, and sex. 

In lines 106-115 (Fig 1), I am essentially selecting the vertices, or nodes, of a particular site_captured, creating a new column called _color_, and assigning them a color (i.e . #D7191c). I do the same with sex, but instead of assigning a color, I assign each sex to a shape. You can use the function: `get.vertex.attribute(graph, "color")` to double check!

**TIP:** Be considerate about the colors you are using, particularly for our colorblind friends. [Here](https://stackoverflow.com/questions/57153428/r-plot-color-combinations-that-are-colorblind-accessible) is just one of many helpful resources for helping you pick a color pallet that is inclusive! 

<figure>
  <img src="https://user-images.githubusercontent.com/78130420/181677484-a2ab4fb2-667f-4654-9218-95c064ba8296.png" alt="fig1">
  <figcaption>Fig.1: An example of assigning node attributes. Note when referencing vertices use V() Tip: an easy way to create a new column: df$new_column_name <- 1</figcaption>
</figure>

I also want to color the edges black between birds from the same site and blue between birds of different sites (Fig 2). This gets slightly trickier, but we are using the same logic here. First, I create a column in _graph_ called `site` (see line 118), then I create a list of birds from each site (lines 119-122). On line 125, I specify that I want all edges to be blue, but lines 127-130 I specify that I want edges between birds in the lists I just created to be black. 

<figure>
  <img src="https://user-images.githubusercontent.com/78130420/181677669-735e4143-121c-4bb3-8ea7-757074cfa45d.png" alt="fig2">
  <figcaption>Fig. 2: An example of assigning edge attributes. Note when referencing edges use E(). alpha() allows me to set the opacity of the color. I like to make edges somewhat see through so you can tell where they overlap, and I think it is generally easier on the eyes when you have highly connected plots. It allows you to use a darker color without it looking too heavy.  </figcaption>
</figure>

**Now, I'm ready to plot! I'm using the igraph function `plot()`.**
 
First, I'm going to specify that I am plotting my network object, called _graph_ (Fig 3). I use the  `layout =` arguement to force a layout. [Here](https://r-graph-gallery.com/247-network-chart-layouts.html) is a description of some basic layouts. Next, I am going to specify what I want my vertices to look like with arguements like `vertex.color`, vertex.frame.color`, and vertex.shape`. This is where I am going to reference the columns I created in my network object earlier. I will do the same for my edges and specify that I want the width to correspond to the number of times the verteces interact (to depict relationship strength). It's a personal preference and depends on what you're plotting, but I like my network edges curved! If you don't specify `edge.curve`, the default is staight. Lastly, I format the position of the labels relative to the vertex and the color. I also set the title with `main =`.
  
  <figure>
  <img src="https://user-images.githubusercontent.com/78130420/181677787-d7b0935b-4ad2-4c18-8cd6-04e9c120b5dd.png" alt="fig3">
  <figcaption>Fig. 3: Lets put it all together and specify our attributes and aesthetics! </figcaption>
</figure>
  
 Finally, `print(netXbin)` outputs my network.  

  <figure>
  <img src="https://user-images.githubusercontent.com/78130420/181677868-08e893c2-280f-412d-b35c-111edb66caab.png" alt="fig4">
  <figcaption>Fig. 4: The final product! </figcaption>
</figure>

I hope this was helpful! Remember, when you find yourself fighting with R and you just can't get something to work, Google it. Odds are someone has worked through a similiar problem and graciously posted their solution. Websites like [Stack Overflow](https://stackoverflow.com/) are extremely helpful for getting you started or finding inspiration. You can then adapt posted solutions to best serve you. This is exactly how I worked through _many_ issues. 
 

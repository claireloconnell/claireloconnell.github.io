---
title: 'Custom layout'
date: 2022-07-29
permalink: /posts/2022/07/networklayout/
tags:
  - notes
  - resources
---
If you have been playing around with network aesthetics, you have probably spend some time trying to figure out **what layout works best to represent your data**. After all, network's can be a great way to represent many complex relationships in a meaningful and digestable way. So, this step should not be underestimated! Thankfully, igraph has several [layouts](https://r-graph-gallery.com/247-network-chart-layouts.html) you can use. 

These layouts might not be _exactly_ what you're looking for. No worries, you can create a customizable network layout! I'm going to walk you through how I created a custom layout! **Fair warning:** it is a bit cumbersome and not the most efficient code (alternatively, I would suggest using a forloop), but it works! Please proof and fully test all codes for your own use.

For this tutorial, I am building off of my [previous post](https://claireloconnell.github.io/posts/2022/07/networkaesthetics/), so check that out first! 

So, we are starting off with this network: 
![Screenshot (121)](https://user-images.githubusercontent.com/78130420/181688859-e62e1ca1-0be1-4255-96a9-c8762f4d0c96.png)

Not bad, but it could use some work! Some of the nodes are clumped together such that there is a decent amout of white space and the edges, especially the blue edges, are getting lost among the black. I can fix this if I organize the nodes by site to really emphasize the relationships across site. This way, vertices from the same site will be plotted in a circle in one of four quadrants of the plot. My plot should look a little something like this:

![Screenshot (123)](https://user-images.githubusercontent.com/78130420/181693930-d111434e-bfd2-468a-80dc-2b4164572ab9.png)

So here is my plan:

For each site,
1. Subset my edgelist by site captured 
2. Create network object 
3. Manipulate x,y coordinates 
4. Combine manipulated x,y coordinates into 1 df
5. Plot! 

First, I subset my edgelist to only include interaction data between actors and subjects of a particular site (Fig.1). I ran into trouble when I tried to create a network object with attributes, and I quickly realized that igraph struggles when the number and/or identity of the individuals listed in the edgelist does **not** match the attribute list. So, I filtered my attribute data as well. 

![Screenshot (124)](https://user-images.githubusercontent.com/78130420/181697293-60ab15ba-7660-4bdf-b2bf-98614886e6fc.png)

Once I had my network object, I used the `layout.circle()` function to get the coordinates. I converted the list into a dataframe, renamed the columns, and added what site these coordinates belonged to (this step is mostly to keep myself organized). 

Then I manipulated the x and y coordinates depending on where I wanted them to go. If I wanted them in the top right corner, I added the same value to both x and y. If I wanted them in the bottom left, I subtracted the same value from both x and y. I played around with what value to add/subtract until I liked the distance between sites, in my case the value I went with was 2.

![Screenshot (125)](https://user-images.githubusercontent.com/78130420/181697398-81929b16-2c7d-4971-a3c2-760fae42709f.png)

After I ran through this process for each site, I combined each site df into one df. At this point, I realized I was going to need the coordinates to coorespond to a particular individual (just having the points coorespond to a site generally wasn't going to work since I was planning on repeating the same networks. So, for consistency's sakes, I needed each point to be in the exact same spot across plots). To accomplish this I merged my custom layout with my attributes df and selected the columns of interest. Then I converted the df into a matrix using a custom matrix function called matrix.please.
<pre>
 matrix.please<-function(x) {
                    m<-as.matrix(x[,-1])
                    rownames(m)<-x[,1]
                    m
                  }
</pre>
![Screenshot (126)](https://user-images.githubusercontent.com/78130420/181697475-efe10c0c-8243-45c6-9139-4dc0e3ac2d14.png)

All that was left was to plot my edglist (that included **all** sites) and specify my custom layout! 

![Screenshot (127)](https://user-images.githubusercontent.com/78130420/181697570-d1116088-b2f2-454c-91df-948749efd794.png)



---
title: 'R: the basics'
date: 2013-08-14
permalink: /SNA-blog/basics/
tags:
  - R
  - data
  - basics
---
I want to share how I approach the basics data analysis in five steps: 
1. Import
2. Clean
3. Wrangle
4. Summarize
5. Plot and test

This is by no means comprehensive, but I hope to provide a generalizable framework that makes the process of data analysis more approachable!

_Tips_:
R Markdown files are a really great way to stay organized while coding. I prefer RMD files (compared to R scripts) because t
R projects are useful for keeping track and organizing related files
<figure>
  <img src="https://user-images.githubusercontent.com/78130420/147553215-9077d47a-5cc0-4d35-ad7c-672a7d87ed7b.png" alt="rmd">
  <figcaption>Here is an R Markdown (Rmd) file. This is how I like to set up my interface in R.</figcaption>
</figure>

Import data
======
First things first: import your data! Like with most things in R, there are many ways to do this. However, for reproucability and collaborative purposes, it is best practices to make sure your code runs efficiently. 
This is also a good time to install packages and load your library. 

**_Helpful functions_**
`read.csv()`
`read_csv()`
`install.packages()`
`library()`

First looks and cleaning 
======
Once your data is imported, make sure you get a good look at your raw data and figure out what you need to do to tidy it up. Here, you want to make sure yo
**_Helpful functions_**
`unique()`
`length()`
`nrow()`
`lubridate::as.Date()`

_Tips_
Dates and times are notoriously tricky to work with in R, don't get disouraged!
From a data ethics standpoint, it is important to make sure you aren't misrepresting the data.

Wrangling 
======
Now that your data is nice and clean, its ready _to get ready_ to work with! Here, we need to make sure we have all of the information we need to test our hypothesis. 

**_Helpful functions_**
`unique()`

_Tips_
This is the best time to have a plan! Write yourself a To Do list or write pseudocode to be your guide. This keeps you organized and on track. 
When in doubt, just Google it! Odds are someone has run into the same error you have and have graciously posted the solution. Websites like Stack Overflow are very helpful!

Summarizing 
======
At long last, your data finally ready to test your hypothesis!
Here is where you get to make sense of your data by summarizing 

**_Helpful functions_**
`Filter(), select(), subset()`
`group_by(), unique()`
`summarizey(), mean(), n()`

_Tips_
At this stage, its easiest to have a plan for how you want to best visually represent your data. This means deciding what kind of graph you are going to use and what data do you need to make the graph. With a plan, it is much easier to understand how you need to summarize your data. 

Plotting and hypothesis testing
======

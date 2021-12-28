---
title: 'R: the basics'
date: 2013-08-14
permalink: /posts/basics/
tags:
  - R
  - data
  - basics
---
As I learn to navigate R and coding best practices, I realized a crucial first step is _getting organized_. Staying organized is another challenge in and of itself, but it is much easier to do if you have a solid plan for your code. Thankfully, there are tons of ways to make sure your start on the right track and stay organized along your coding journey. I want to share how I approach the basics data analysis in five steps: 
1. Import
2. Clean
3. Wrangle
4. Summarize
5. Plot and test

This is by no means comprehensive, but I hope to provide a generalizable framework that makes the process of data analysis more approachable! This post assumes you are familiar with R Studio, but I will my best to include information and resources that are helpful for beginners. 

_Tips_:

**R Markdown** files are a really great way to stay organized while coding. I prefer RMD files (compared to R scripts) because to you can combine text with code for easy annotations and notes and break down coding chucks to keep you on track and goal-oriented. 
R projects are useful for keeping track and organizing related files. You can create projects that contain different associated scripts. This way you have all data and associated code in one convenient location. 
<figure>
  <img src="https://user-images.githubusercontent.com/78130420/147553215-9077d47a-5cc0-4d35-ad7c-672a7d87ed7b.png" alt="rmd">
  <figcaption>Here is an R Markdown (Rmd) file. This is how I like to set up my interface in R.</figcaption>
</figure>

Import data
======
First things first: import your data! Once you import your data, you can find it in your environment and start working with it. Like with most things in R, there are many ways to do this. However, for reproucability and collaborative purposes, it is best practices to make sure your code runs efficiently. This is also a good time to install packages and load your library. 

**_Helpful functions_**

`read.csv()`
`read_csv()`
`install.packages()`
`library()`

_read.csv() and read_csv() are very similar but not quite the same! You can read more about the difference [here](https://medium.com/r-tutorials/r-functions-daily-read-csv-3c418c25cba4)_.

First looks and cleaning 
======
Once your data is imported, make sure you get a good look at your raw data and figure out what you need to do to tidy it up. Here, you want to make sure the data were imported in the right format and check for data entry errors like typos.

**_Helpful functions_**
`unique()`
`glimpse()`
`head()`
`nrow()`

_Tips_
Dates and times are notoriously tricky to work with in R, don't get disouraged!
From a data ethics standpoint, it is important to make sure you aren't misrepresting the data by changing any of its inherent properties. The point is to get your data in a workable format for future analyses.

<figure>
  <img src="https://user-images.githubusercontent.com/78130420/147608265-929f9bc1-3a85-4ecc-a3e3-fae2f08db132.png" alt="rmd">
  <figcaption>Here is an example of how I might approach importing and cleaning the data.</figcaption>
</figure>

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
`filter(), select(), subset()`

`group_by(), unique()`

`summarize(), mean(), n()`

_Tips_
At this stage, its easiest to have a plan for how you want to best visually represent your data. This means deciding what kind of graph you are going to use and what data do you need to make the graph. With a plan, it is much easier to understand how you need to summarize your data. 

Plotting and hypothesis testing
======

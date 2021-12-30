---
title: 'What I learned teaching R'
date: 2022-01-04
permalink: /posts/lessons-learned
tags:
  - R
  - notes
  - learning
---
As a graduate student, I teach undergraduate-level courses offered by my university. In the fall of 2021, I was a teaching assistant (TA) for [Analytical Tools for Behavior Information](http://hobsonresearch.com/index.php/biol2099-analytical-tools-for-behavior-information/) taught by my advisor. For someone, such as myself, just starting to scratch the surface of all that is R, this was an awesome experience. I strengthened my own understanding of coding best practices, troubleshooting, and how to talk about code. 

**I want to share some of the things I learned about learning to code in R Studio** 

There are different languages involved in coding like R, html, Python, and JavaScript, just to name a few. Although they are similar, they are not quite the same. Like the majority of the posts in this blog, I will focus on R. 

**1. Learn _what_ to ask and _how_ to ask it**
Learning how to code essentially involves learning a new language. This can be a duanting task in and of itself, and if you're like me, coding isn't intuitive. When I was first introduced to R I had trouble wrapping my head around the basics (what it is, how it works, and why) and, on top of that, I felt like I was getting lost in the terminology and jargon. So, it was difficult to even ask questions. I didn't know _what_ to ask let alone _how_ to ask it.

If you're learning to code, you've probably spent some time Google-ing how to solve a problem. There are _tons_ of resources available to help you learn more and troubleshoot your own code and there are dozens of different ways to write code that does the same thing. But you might have run into the same issue I had: understanding the solution!

This, in my opinion, is the biggest learning curve. I hope to write another post about how I made sense of it all. Being able to understand and communicate code is a skill you have to develop. For me, I had to start with the basics: what is an **object** and what does it do? What are packages and how do you use them? What information does a particular function need to work properly? There was a lot to learn and I didn't quite understand the way people where trying to explain it. I took a lot of notes, watched a lot of YouTube videos, and asked so many questions. 

When I first started to teach R, I saw a lot of my students struggle with the same problem. They were confused but not sure exactly what they were confused about or how to clarify their questions. Being able to walk through assignments with them helped me understand how to break down R language and the logic behind our code. 

My advice is to do the same, hang in there and practice! I learned a lot through trial and error. With this blog, I hope to help people, like myself, who find R to be intimidating but are ready to give it a shot! 

**2. Get organized and (_do your best to_) stay organized**
Set yourself up for success! Spend some time getting yourself organized so that staying organized as you go is much easier. There are a ton of ways to do this, and as I have mentioned before, my favorites (and the simplest organizational tools) are making a plan (and sticking to it), creating R projects, using R Markdown files (instead of R scripts), annotating your code, and using repositories like Github to share and collaborate. 

It is very easy to get lost in a coding rabbit hole, so starting off with a plan keeps you on track. Writing **pseudocode** will give you a framework for what you need to accomplish. It's also a safe gaurd against **p-hacking or harking**. Having a clear goal and a plan for how I might execute the goal has helped me better understand the _tools_ (i.e. specific packages and functions and the logic behind the code) I need to solve the problem. 

Creating a Project, creates a folder that houses any data you will need and related scripts you create. This is a great way to organize files. I also like R Markdown files because you can incorporate writing and notes into your code and knit your files into a nice, neat PDF or html file. A major plus for me is that it is aesthically pleasing. Looking at huge blocks of code is a real eye sore, and creating an outline to break-up code blocks is not only helpful for organization, but it's much nicer to look at. 

You should also annotate your code as you go! You can "comment out" codes with a `#` before any text. This means R won't try to run this code. I use comments to describe what each line of code does, so my future self or collaborators can understand what I am doing!

Speaking of collaborators, online repositories, like [Github](https://github.com/) are helpful for sharing code! We use Github in the lab for sharing code within and across labs. Its also nice for storing back-ups. 

Organization was a huge pitfall for some students. It's very easy to get lost in your code and to pick up where you left off after a break. The students who better annotated their code had a better understanding of what each line of code did, and they were better at adapting code from previous assignments as they moved along to harder coding challenges. 

**3. Talk it out**
If possible, talk through your code and/or plan with someone. They might catch something you miss or give you some reassurance that you are on the right track! As my advisor likes to say, "nerd-snipe" someone! For me, this looks like sighing very loudly in my office until my lab mates kindly offer to help me troubleshoot. Sometimes I ask _"Does this make sense??"_ or I ask if someone has a moment to just listen to my goal and plan. Sometimes I draw what I want a graph or dataframe to look like to help get an idea of how to go from raw data to a final product. 

My lab mates have been an invalable resource for me as I learn to code. They are at varying stages of their coding experiences and they have unique ways of thinking about how to approach a particular problem. We even created a Coding Club to brainstorm, troubleshoot a problem we might have, and to show off our code! I'd be lying if I said R didn't test my patience, but having a literal R support group has made all the difference!

As a TA, I got to see all of the creative solutions my students took to solve the same problem. Some where really clever and they were able to find shortcuts and tricks that I didn't see before. Sharing tips and tricks and talking through how to solve the problem was really helpful.  

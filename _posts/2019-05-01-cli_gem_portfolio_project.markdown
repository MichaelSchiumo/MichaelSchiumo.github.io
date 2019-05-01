---
layout: post
title:      "CLI Gem Portfolio Project"
date:       2019-05-01 16:31:23 -0400
permalink:  cli_gem_portfolio_project
---


First things first, I am not a fan of scraping. Parsing the HTML and finding the correct elements to pass to the scraper methods is one difficult undertaking. However, with the help of one very kind Flatiron instructor, I was finally able to find the correct elements and tags, as well as work through parsing a form and mitigating duplicate results. 

I think that one of the most important things that I've learned through this project is the ability to set up a gem, bundle, and create a repo. All of these seem very basic, but, coming from a new developer-in-training, they aren't necessarily the easiest things to do. For one, there are a lot of issues that can arise, especially when setting up dependencies in different files. My most obvious issue is remembering to commit changes; for some reason, I just get so sucked up into coding that I will write out half of a class before remembering to commit the changes that I've made. It goes without saying that, in the real world, committing often and accurately is one of the stepping stones to becoming a competent developer, as well as being able to work with a team. 

I found the walkthrough for Daily Deals (https://github.com/learn-co-curriculum/daily_deal) by Avi to be extremely helpful. Within this lesson, he shows not only how to write out the project, but how to conceptualize and plan your approach to coding it. Naturally, Avi makes everything look effortless, which was not the case when I was coding my project. Additionally, using this repository of the simple gem Daily Deals, I was able to refactor a lot of my code, especially in my CLI class, where I had repetitive code; always remember: DRY! 

This is also the first time in which we implemented different classes, and had to initialize and pay close attention to what is a class method and what is categorized as an instance method. For instance, one of the issues that I was having with my scraper was receiving duplicate objects in my @@all array. Naturally, we know that @@all is a class variable, as it has two @ symbols. In order to solve this problem, I applied the method *uniq* to @@all, and this solved the issue. Now, my application knows to only pass in objects through my scraper once. 

The concept of my project is pretty simple - I scraped a website that shows the Top 50 books of all time. Thus, my CLI gem allows a user to 1) see all of the books in a list, 2) access information about the book, such as rank, author, and title, 3) and select an individual book by entering an index into the command line. 

If you would like to see the finished product, you can find it here: https://github.com/MichaelSchiumo/books

Good luck to anyone embarking on this project!

---
layout: post
title:  "Some notes on building a a working cli gem"
date:   2017-04-20 22:06:20 +0000
---

## `CookingClasses` gem

If I am going to write a gem, I would like it to be something I am in love with. So without second thought, I know I want to make a gem about cooking and food. So I decided to make one to show Customers' favorites cooking classes at Sur La Table. 

To start, I checked out the sur La Table website, https://www.surlatable.com/category/cat2211278/In+Store+Classes. Played around it and figured out the possibilities to scrape the lesson name, url, menu and description. 

After installation, user will be able to select from a list of cooking classes offered at Sur La Table. For more information, they can input the class number and class description and menu will be displayed. I have a `CLI` class for holding all the user interfaces and collecting user input, and a `Lesson` class for my lesson object and instance method to scrape data.

Everything seems fine as I developed my coding, but when I run the gem I have trouble with  loading files, etc. It is a little confusing about requiring the files. At a point I was able to run the gem by `ruby bin/cooking_class`, but I was not able to run it simply by `cooking_classes`.

After a few more test and trial and googling, I realized all my issues lie in `CookingClasses.gemspec`. I have to manually change a few items  for the gem to work.
`spec.files = ["everything in the /lib"]
spec.bindir = "bin"
spec.executables   = ["cooking_classes"]`

After I made these changes, I can successfully run the gem by typing `cooking_classes` after `rake install`

While working through the project, i have got a deeper understanding of many methods. For example, case statement, which seems very simple until validate your user input which can be either numbers and strings. To collect just a range of numbers, i tried using `regex` and `.to_i.between?`, and both faild.  I could have done this easily with if else statement but it made my code really long and messy.  I finally figured using an `array` provides the neatest code. 

All in all, I am glad to be able to apply what i have learned in ruby in creating this cli gem. 




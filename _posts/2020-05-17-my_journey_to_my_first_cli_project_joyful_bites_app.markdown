---
layout: post
title:      "My Journey to my First CLI Project: Joyful Bites App"
date:       2020-05-17 20:08:52 -0400
permalink:  my_journey_to_my_first_cli_project_joyful_bites_app
---


# Planning Stages

First, it’s important to understand what exactly is the objective of this project. We were asked to create a CLI using dry Object-Oriented Ruby code that highlighted our understanding of class vs instance methods, self, object instantiation, initialize, shebang line, if/else conditional statements, method return types, variable scopes, iterating through collections, index, arrays, hashes, strings and more. Just in case you were wondering, dry code simply means concise, easy to read code where you do not repeat yourself.  In the 1960’s, CLI’s were the only way for humans to interact with computers. According to w3schools.com, CLI is still being “used by software developers and system administrators to configure computers, install software, and access features that are not available in the graphical interface.” This speaks volumes as to why the master teachers at Flatiron School have asked us to embark on the journey of building a CLI as our first solo portfolio project. 

 I had never heard of “CLI” before I started this coding bootcamp program but I learned in our “Tic Tac Toe” lab it means Command Line Interface. The command line lives in your terminal and is where the user can run commands in the program.


The user is presented with a text-based interface where they can view files and send commands. A response is sent to the user with a list, table or message to select from. The outermost level of your own operating system is called a shell. In my case, I have a macOS and my shell is called Bash. This Bash shell is the software that controls the Command Line Interface. Also the directory is your folder, where all your files for your project will be created. Below are some helpful CLI commands that will be very important to remember as you get started with your project. 

 For my project, I decided to go one level deep. The user can interact with the program and receive back detailed information based on an option they choose. My goal was to create an app whose strength was found in the simplicity of the architecture and easy to use commands to retrieve back information based on what meal idea you selected. As our world is undergoing a global pandemic, I thought it was fitting to create an app that helped families and people of all ages to come up with fun meal ideas to cook together. The user also can view the specific ingredients needed for each step and detailed recipe instructions for each meal. I know that for my family, it is not always easy to make it to the grocery store to get all of our favorite ingredients while the stay at home orders are still in effect. Therefore, my app takes away the struggle for you of having to think about what meals to make and allows you to type in the specific ingredient(s) you have available in your fridge, kitchen or pantry. My Joyful Bites app gives you back a list of ten delicious meal options for you to pick from. I also added an option if the user is dairy-free, gluten-free or Vegan and they simply need to type in ‘Vegan GF’ to receive back these dairy-free, gluten-free and Vegan friendly meal options!

# API

API stands for Application Program interface. It simply represents a messenger that takes requests and tells the system to do what you want and returns a response back to you. An API stores JSON objects and data and instances of a person. You can think of an API like a waiter running back and forth between the customers who are making their meal options and the chefs preparing the meals chosen. In this case the API, like the waiter, is running back and forth between applications, databases and devices to deliver data and create connectivity. 

I decided to go with retrieving my meal data from a wonderful API called Spoonacular. You need to first make a free account and read over the authentication document for the API to learn how to set up your own personal API key and how to use it going forward in your project. An API key is a unique identifier that controls your access to an API service provider. The API key starts to keep a record of how many calls are made to the API by the user and what areas the user can access. This is why the Spoonacular API denied my access after 150 calls, and told me to upgrade my plan or else I would not have access to the API to finish my project. Here is a link to the documentation for the Spoonacular API key. `(http://spoonacular.com/food-api/docs#Authentication)`

Keep in mind, if you choose to use this API you will need to purchase the next plan up from the free plan, because after 150 points you are locked out from using your API endpoints in your project. I went with the cook plan. It was worth the purchase though, because it upgraded me to 1500 points a day and allowed me to work on my project all day without locking me out. Also remember that all plan payments charge you monthly and can be cancelled at any time. I recommend canceling after you pass your technical assessment.  

I chose to work with an API, rather than scraping, because scraping is a rather outdated practice now in the tech coding industry and I wanted to learn a new skill that would be beneficial for me, my future projects and future employers. I also found that with scraping, there is a possibility that the site you are scraping data from can be altered, taken down or moved to another domain which could affect your CLI project. Although, that is not to deter you from choosing to scrape your project, but for my project an API worked best to help me achieve the end results that I wanted visually and for happy user satisfaction. 

# Coding
(insert flow of app pic)


My approach to coding my Joyful Bites app was efficient, systematic and visually appealing. I wanted the user to enjoy their experience in my app and be able to code something that could give the user back colorful and vibrant messages that greeted them both hello and goodbye. 

Some questions I considered when building my Api Class and self.get_meals class method were as follows: 
* 


The hardest part to decode was how to best set up my Api class. This Api class would get my information and return back the information to the user. I found making this Api class to be challenging because I had to use two data Api endpoints to retrieve back the information I needed for my user and parse through the ingredients array and the analyzed instructions array. My strings of information needed were stored in an array of hashes. This proved to be a challenging and tedious task but was very fun to use methods such as first, map, flatten, bang operators, if conditionals needed to get back the ingredients and recipe instructions to move the project forward. 


I really I relied on binding.pry to pause my code at a specific line and poke inside to see what was inside my arrays and I was going to achieve retrieving what I wanted out of the arrays. It is essential you start getting comfortable with binding.pry as you progress through this Flatiron program and beyond. 



Some notes I considered when building my Meal class were as follows: 
* 




I created a bin folder which had my executable file I called “run” that was the command most called in my project because it runs your entire program. I also had a library directory which had a meals folder that held my Api class, my Cli class, my Ingredient, my Meal class and environment.rb class. I also had to follow steps to hide my api key before I published it to my github repository, by making an .env file that stored my personal spoonacular key. The reason why it is important to hide your key is for protection and security purposes, so that no one can ever get access to your key and turn off your own access to your program. This link walks you through step by step on how to hide your API key. (http://dev.to/kcarrel/major-key-alert-hide-your-api-keys-l4c)



I also recommend keeping a running list of all the times your program hits an error based on the specific combination of what you typed and selected choices. You want to stay consistent with what you try in binding.pry and this way, you can go through each error one by one, until you have solved each one and your program runs more smoothly. It can be daunting to debug your errors but after a while you will get more used to tackling how to solve your error messages best. 

# 10 Helpful Tips

1. Take one day to research and choose your API or Scraping Website. I took many days to research and this delayed the first stages of my project. Use this first day to also fully understand what the project asks of you, understand all the requirements, read over your API documentation or how you will exactly be scraping the website of your choice. 

2. Use your family members or friends as rubber duckies, you will NEED to speak out your logic and ideas to someone even if they don’t exactly understand all that you are referring to. This will also be great practice before your assessment.


3. Write out a detailed plan for each day you will work on your project with deadlines for yourself and specific tasks you need to accomplish by a certain time. Ask a friend, coding classmate, spouse or family member to keep you accountable if you feel like you need the extra push or source of inspiration. 


4. If you are in the full-time or part-time cohorts, consider attending ALL of the open office hours pertaining to project support held by your cohort leads. You will not be allowed to ask for any help from Ask A Question technical coaches, so it is imperative you utilize the help from your cohort lead and classmates. If you are in the full-time cohort you will have one week of project support but if you are in the part-time cohort, you will be given two weeks of project support. My cohort lead was kind enough to make our project support office hours spanning for two hours long and she added an extra Saturday office hours meeting right before our deadline in order to answer all of our questions! 


5. Demo your project to your family, friends or cohort lead! Be open to constructive criticism, even from people that do not read code because they may be able to find some errors or give you some creative ideas on what they would like to see as a user of your app. 


6. Take many deep breaths when you feel overwhelmed with how much you still need to finish, write down one thing you want to accomplish during that coding session. This way you can make your time more goal-oriented and feel like you are making progress.


7. Schedule your technical assessment at least a week early, before the final deadline just in case you need to schedule another assessment if you did not initially pass the first one. 


8. Don’t stress, feel blessed! You got into this amazing prestigious coding school, Flatiron, and feel confident that you will make it to the end! Get excited each morning and night when you work on your project!


9. Make sure to move, stay active and take long walks outside to enjoy some fresh air for your brain. It’s important you step away from your code to be reinvigorated and energized when you come back to code! Who knows? Maybe taking in some fresh air away from your computer  may have helped you think about how to carry out a solution to one of your errors along the way!


10. Have fun! It’s not worth it to code this huge project without smiling and enjoying the process! We are all just starting out on our coding journey and giving ourselves grace to mess up and learn is very crucial! Enjoy every second of this Cli project! 

# In the Future

As I continue to evolve this app, I hope to turn the Joyful Bites app into a gem that people can download for themselves and use to make their lives so much easier! I plan to add more nutritional information for the user to receive back. For example, I want the user to not only receive the meal options, ingredients needed for each step and the recipe instructions but I also want them to be able to see the calories and nutritional facts about the meal. I also want to incorporate a way for users to see various reviews on the meal and tips other Joyful Bites users have found helpful when cooking this meal. I also want the user to be able to rate the meal, with 1 to 5 starts, after they have cooked it. I want to modify the output of the recipe instructions string to be changed to an index and numbered. Lastly, I want to include prep time needed to create this meal, alternate ingredients that can be used to make the meal

# Shoutouts

I want to thank my cohort lead teacher, Dominique De Leon for her tireless help with answering all my questions and her encouragement throughout the culmination of this project. I also want to thank my fellow classmates in my cohort that were also readily available to pair program with me, offer constructive criticism that made my code better and were always kind enough to answer my questions. Lastly, I want to thank my parents, Pedro and Nancy, and my dear sisters, Karol and Jean, who were all my constant source of support,creativity and love. Without my family, I would not have been able to keep going. Most of all, I am very grateful to God for the grace and strength He provided for me to be resilient and finish this incredible project. 



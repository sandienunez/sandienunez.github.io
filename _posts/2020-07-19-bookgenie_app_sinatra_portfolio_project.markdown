---
layout: post
title:      "BookGenie App: Sinatra Portfolio Project "
date:       2020-07-19 21:26:18 -0400
permalink:  bookgenie_app_sinatra_portfolio_project
---



![official bookgenie logo](https://user-images.githubusercontent.com/61069416/87862974-e9b1bf80-c923-11ea-8d32-baec0a2d25e5.png)
## Planning Stages

Creating my second Flatiron project was an intense but a highly educational experience for me. I learned so much everyday of the project build and owe it all to a strong foundation that the Flatiron school gives us through our classes and curriculum that covers so many core concepts and coding assignments that led up to our second project. For this MVC, CRUD app I used Sinatra and Active Record to create BookGenie, an app dedicated to help you solve that reading problem you have. You know, the one where you have 309420394 books ordered from Amazon stacked up and dusting on your reading shelf that you have yet to read for the millionth year in a row? BookGenie allows a user to create a custom BookGenie list where they can store all the books they want to read. They can create, edit, update and delete the book objects and can also choose the book title, book author, genre, number of pages, projected start and end date of reading the book, customized times they can commit to reading the book and select if they have read the book or not yet. BookGenie helps you create a reading schedule that will help you finally finish all those books that have been on your reading booklists since high school!  

It's funny how the evolution of a project's trajectory progresses. Initally, the app was called BookMine, then BookMark and now BookGenie. I was inspired by the Disney film "Aladin" where Genie sings a famous song called "Friend Like Me." The logo, the website aesethetics, color schemes and whole project layout was built after this movie and song. Please enjoy the fun welcome page!

With how fast paced social media, the news outlets, techonology and more is evolving, it can be hard to not be distracted and make time to finally check off those books that have been on your booklist for ages. My intention was to take away the stress of planning when to start and end your books and help you find suitable times in your daily schedule to fit 5 minutes of reading. Everyone has 5 minutes to spare! Many studies have shown how reading can decrease stress levels, help you have more empathy, leave you feeling inspired and spark creativity or understanding in other projects you are working on! Use BookGenie during this COVID-19 crisis to unleash your inner bookworm and read (as Lionel Richie would say) all night long! All night long!!!

Because of my love for music, I thought it would be facinating to create a home page called the "Reading Cafe" where the reader can stay on the website and actually read their books while they listen to a special BookGenie curated playlist on Spotify or through .mp3 songs coded into the home page. During this pandemic and quarantine, I wanted to build a digital location where readers from all over the world can come together and listen to music that could inspire their imagination and help create a peaceful environment as they read!

## Coding

Coding this entire project was a lot of fun, but it came with many challenges and error messages to decode. First, I needed to decide what I wanted to give the user access to and how many models and controllers I was going to make. I chose a user model and book model. My book model belongs_to a user, and my user model has_many books are the relationships I established. 


![Screen Shot 2020-07-19 at 10 22 08 PM](https://user-images.githubusercontent.com/61069416/87893618-6c16ae00-ca0e-11ea-95e9-5e54be2c6e6e.png)
![Screen Shot 2020-07-19 at 10 22 14 PM](https://user-images.githubusercontent.com/61069416/87893621-6e790800-ca0e-11ea-8113-3ca2074e235f.png)

Remember, the convention is that models are singular when named and essentially everything else is plural when named.
![Screen Shot 2020-07-19 at 10 26 41 PM](https://user-images.githubusercontent.com/61069416/87893811-f6f7a880-ca0e-11ea-9675-0655bdf44412.png)



MVC stands for models, views and controllers. It is an architectural pattern that coders use to create order and apply separation of conerns in their projects. Following an MVC format also helps to better understand each other's work. Thankfully, running bundle install on the corneal gem was an easy way to get my file structure all in order before I started coding. 

![Screen Shot 2020-07-19 at 10 41 02 PM](https://user-images.githubusercontent.com/61069416/87894519-fb24c580-ca10-11ea-971e-bdbf9c259fc4.png)

CRUD stands for create, read, update and delete. They are four basic functionalities that coders use to make web apps and are essentially a set of CRUD actions that a user can make using Active Record.


![Screen Shot 2020-07-19 at 9 30 17 PM](https://user-images.githubusercontent.com/61069416/87891666-ba28b300-ca08-11ea-9c33-111e2bfb57ec.png)

These are the requirements I made sure I understood before coding in order to pass this project.
![Screen Shot 2020-07-19 at 9 31 54 PM](https://user-images.githubusercontent.com/61069416/87891670-c01e9400-ca08-11ea-8f39-2cd8246adf6d.png)

Here is my schema, where I needed to make a database, create a table, run migrations, seed the database, add columns and seed my data by running 'rake db:seed' in the terminal. 
![Screen Shot 2020-07-19 at 9 46 36 PM](https://user-images.githubusercontent.com/61069416/87891844-5fdc2200-ca09-11ea-9e45-1cf2237768fa.png)

Below is a handy list of commands I found useful during this project and that you can run by running rake -T.

![Screen Shot 2020-07-19 at 9 48 42 PM](https://user-images.githubusercontent.com/61069416/87892416-0aa11000-ca0b-11ea-9e8e-750a57c1ca2a.png)

This incredible table created by a Flatiron graduate, Jason Arnold, depicts the seven restful routes we learned in this module and that we needed to apply in this project. It is a very helpful table that breaks down each request. I learned that we render views and redirect to routes.

![1_slrwqTXKO6evtPn5YVWR2Q](https://user-images.githubusercontent.com/61069416/87892314-c6157480-ca0a-11ea-9d80-c521de7f372a.png)


Here are the common error messages that I received throughout the project that had to do with missing a slight / or a ' ' or had to do with redirecting to correct routes. 

![Screen Shot 2020-07-11 at 7 09 05 PM](https://user-images.githubusercontent.com/61069416/87890515-eb9f7f80-ca04-11ea-90a1-2e258d5bee44.png)

![Screen Shot 2020-07-14 at 2 19 02 PM](https://user-images.githubusercontent.com/61069416/87890523-ef330680-ca04-11ea-985c-2db0ea73d20e.png)

![Screen Shot 2020-07-14 at 1 06 41 PM](https://user-images.githubusercontent.com/61069416/87890511-e5a99e80-ca04-11ea-97e0-5248001f8232.png)

![Screen Shot 2020-07-18 at 1 47 28 PM](https://user-images.githubusercontent.com/61069416/87890301-e988f100-ca03-11ea-8fbb-27b6cc653bcb.png)

If you have a Mac and are having issues with a corrupted database as I was, make sure to force quit ruby in your active monitor frequently throughout your coding sessions. Do this by typing ruby in the search engine when you click active monitor and click the x to the left of ruby. This will save you a lot of time on labs and this project!

![Screen Shot 2020-07-13 at 9 00 18 PM](https://user-images.githubusercontent.com/61069416/87890473-b3983c80-ca04-11ea-9a1a-3d5c3a4611b9.png)


This is how I coded the my post books route that gave me the most trouble. First I needed to create a new book object and pass in params or in my case, all of the attributes I had chosen for each book object. 

![Screen Shot 2020-07-19 at 9 12 46 PM](https://user-images.githubusercontent.com/61069416/87890512-e80bf880-ca04-11ea-95c4-3f95298b6939.png)




The following images depict what a user sees visually upon logging into BookGenie, entering the home playlist page and how a user can create a book object by filling out a form. In order to bring my ideas for this project to life, much embedded ruby was used in the the view erb files, ruby code in the controllers, as well as css and html for styling purposes. 

![Screen Shot 2020-07-18 at 4 15 54 PM](https://user-images.githubusercontent.com/61069416/87890507-e17d8100-ca04-11ea-9c16-86b503c757b3.png)


![Screen Shot 2020-07-16 at 3 02 27 PM](https://user-images.githubusercontent.com/61069416/87890536-fce88c00-ca04-11ea-8c8d-86b60971a101.png)

![Screen Shot 2020-07-18 at 1 47 51 PM](https://user-images.githubusercontent.com/61069416/87890299-e42ba680-ca03-11ea-8c02-06bf9e39772d.png)


The most challenging part of the project for me was setting up validations and installing and learning how to display sinatra flash messages. I had a lot of difficulties with getting flash messages to pop up on my web server, but after much persistence and researching I was able to perservere and include flash messages in my project. 


![Screen Shot 2020-07-18 at 11 44 08 PM](https://user-images.githubusercontent.com/61069416/87890296-df66f280-ca03-11ea-9622-f8e152867f33.png)

## 10 Helpful Tips

 1. Choose a project idea that you are crazy passionate about and that you find interesting! Make it stand out, choose something innovative and something that you have not seen created yet. 
 2. Do your homework! Watch all your cohort leads videos and any youtube videos from Flatiron Teachers going over Sinatra builds. Read blogs from other Flatiron students on learn magazine or medium to gage how they approached this project. Also watch some Sinatra projects that show demos of their projects so you can get an idea of how you want your project to look or not to look.
 3. Pray, eat healthy, exercise regularly, take long walks in nature, don't compromise your health to finish this project. Wake up early, do the hard work and believe that God will get you through this challenge!
 4. Have a joyful and postive mindset! Keep telling yourself that you will advance and debug and find a solution no matter what. Period. 
 5. Be aware of distractions, internet or not, stay focused and use the pomodoro method (free app) if needed!
 6. Don't give up! Ask constant questions and ask more and more and more questions. It's how you will be ready for your assessment.
 7. Ask your family, friends or cohort lead for feedback on your project. Don't get offended if they think your project looks like a 1999 html website or super oldschool. Remember, for many this is our first experience creating a real webserver project, so take all criticism with a grain of salt. Always looks for ways to improve your code, layout and overall project.
 8. Set a timeline of when you need to finish your project by, make little goals for yourself along the way and don't forget to treat yourself.
 9. Be gracious! To God and to those around you, maybe it's your family, friends, siblings, spouse or dog. Whoever is supporting you along the way, say thank you! Practice gratitude, everyday write one thing your thankful for while coding this project. It will put everything in perspective and not let you focus on that one erb file or route that keeps giving you a "Sinatra doesn't know this ditty" error!
 10. Be kind to yourself! Don't lose faith that you are an amazing web develepor/ software engineer. You are so special and your project is going to be amazing! Stay hopeful, you will get through this and present a bomb project that will blow your assessor away! 

## In the Future

As I continue to evolve this app, I want to create a seperate tab on the home navigation bar and page dedicated to incentives that assign reading as your reward for finishing important tasks. For example, If I wash my car...finish my laundry...finally file my taxes...wash my dishes, therefore I get to reward myself with a chosen number of minutes of reading for fun! This incentives page would drive people who are externally motivated to reach a target goal each day that they want to read and get to reward themselves with reading after they finish some chores for example or complete an important task on their to do list! I also want to publish this app on a website and buy a domain server for BookGenie. I hope to make this website mobile friendly and create a functional, easy to use and aesthetically beautiful mobile iphone/android BookGenie app that can make it easier for you to scan the ISBN codes of your books and have an option to not only store but purchase books using a Google Books or Amazon API. In the future, I hope to partner with influencers, celebrities or public figures that people find inspirational and feature their BookGenie lists on our website and instagram page. I hope to also let other users see the books their freinds are reading and share book reccomendations through the website/app. Lastly, I would love to do a partnership with Spotify and Audible to encourage more people to read!
## Shoutouts

I want to first thank God for this incredible opportunity to be able to create another coding project that I am crazy passionate about and has been such an incredible learning process for me. God really helped sustain me and inspire me with creativity. He gave me His unending strength, peace and wisdom to bring this project to life! A huge thank you to my cohort lead teacher, Dominique De Leon for her guidance and advice as I navigated my first web server application and her patience as she reiterated the seven restful routes to me again and again. I also want to thank my programming classmates who were so kind to give of their time to explain to me my mistakes and the neverending questions I had. Lastly, I am so grateful for my family, my parents, Pedro and Nancy, and my incredible sisters, Karol and Jean, who all stood by my side as I made my final commit. Without their constant support, I would not have been able to survive while coding this project. They are wonderful human beings. I look forward to starting the third module on Rails this next week and hope to create a new app that surpasses this project very soon!

Please make sure to take a quick moment to check out my github below and slack me at Sandie Nunez to let me know your thoughts on my project, critiques or questions you might have!

## https://github.com/sandienunez/BookGenie/tree/master/app

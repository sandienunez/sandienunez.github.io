---
layout: post
title:      "React-Redux Flatiron Portfolio Final Project- Joyful Bites Bakery"
date:       2021-01-24 21:42:00 -0500
permalink:  joyful_bites_bakery_app
---

## Joyful Bites Bakery app

![JBlogo](https://user-images.githubusercontent.com/61069416/105647206-fafafc00-5e71-11eb-8257-5ee6ee037da8.jpg)

The point of this application is to help customers find a safe healthy haven for their sweet tooth! The Joyful Bites Bakery app allows you to easily view all the dessert items currently available on the menu tab, create a bakery order for your favorite cookie, view all the orders created in the Joyful Bites community nationwide, read about our bakery’s mission and check out our story page. 

## Planning Stages 

During the planning process for my Rails back-end and React, Redux and JavaScript front-end project I was excited to dissect each aspect and complexity of this project. I started by drawing out all the components and elements for the front-end side of the projects. I drew out how I wanted my form and buttons to look like. I also drew out what I wanted my route pages to look like. This helped me to establish how many components I was going to build out and brainstorm what I wanted my relationships and models to look like. I then started mapping out how many models I would need for my project and the corresponding attributes and controllers. I built code "vertically" in order to reduce bugs and errors. This means I built out one action method at a time, one model relationship, made one fetch request and made sure to get back one JavaScript object in the console. This proved to be extremely effective.

Below were my final models for the project.
```
  
class List < ApplicationRecord
    has_many :list_items
    has_many :items, through: :list_items 
    accepts_nested_attributes_for :list_items, :items 
end
  
class ListItem < ApplicationRecord
    belongs_to :list 
    belongs_to :item 
end

class Item < ApplicationRecord
    has_many :list_items
    has_many :lists, through: :list_items 
end 

```
Here are my backend routes for this project:


![Screen Shot 2021-01-24 at 9 29 14 PM](https://user-images.githubusercontent.com/61069416/105654089-4a015b00-5e8b-11eb-87c7-c0773f2cf9eb.png)
![Screen Shot 2021-01-24 at 9 29 23 PM](https://user-images.githubusercontent.com/61069416/105654092-4b328800-5e8b-11eb-880a-3f0e479b5eeb.png")


## App Idea

My objective was to create an incredibly healthy, sustainable and whole bakery with treats that make people feel good. As a person who has suffered from dairy and gluten allergies, I know first hand the difficulty of finding delicious desserts that do not make you feel sick, sluggish, bad about yourself, tired and leave you with an awful sugar crash. When my father was diagnosed with pre-diabetes and extra high cholesterol, I set out on a mission to create the most delicious baked goods that are not only nutritious, dairy-free, gluten-free , anti-inflammatory and low-glycemic but give you the energy you need to do the work God has called you to do.
You do not have to sacrifice "yummy-in-my-tummy" moments or give up your sweet tooth cravings. Everyone deserves the right to enjoy treats, cookies, cakes, fresh-made breads and desserts. Baked goods are meant to make you smile, meant to be shared with the special people in our lives and help make our family/friend celebrations sweeter. Joyful Bites encompasses what America's heart is a lot about, helping your neighbor and serving others. That's why for every one treat you buy, one is given to someone in need.
The Joyful Bites Bakery app is a single-page application that serves two main purposes: Clients can both create and save bakery orders, as well as delete orders previously made and view all the client summaries or list order objects. Clients can also visit 8 different routes including clicking to read the bakery menu items for the day, about us, our story, contact information and see all of the orders made in the Joyful Bites Community Order Feed on each route rendered in the parent App component.

## Restful Routes and CRUD Actions
What exactly is REST? And why is it important? REST stands for Representation State Transfer. It is a set of conventions for structuring our routes and mapping them to CRUD action methods (Create, Read, Update, Delete). They are needed because without the CRUD action methods, our app would not be able to receive the get requests and send them to the corresponding action method names as they are fetched to the API. Below are all the Rest and CRUD actions found in my Listing model. In the future, I plan to build out the edit and update methods for the user to be able to go back and edit their bakery order form they originally submitted.


  | METHOD | ROUTE | CONTROLLER ACTION   | Description |
| ------------- |-------------| ----------- | ------------------- |
| GET  |  /lists | #index | Show all listings | 
| POST | /lists | #create | Create a new listing
| GET  | /lists/new | #new | Render form for creating a new listing|
| GET  | /lists/:id/edit | #edit | Render form for editing a listing  |
| GET  | /lists/:id | #show | Show a single listing |
| PATCH | /lists/:id | #update | Update a listing |
| DELETE | /lists/:id | #destroy | DELETE a listing |

## Lifecycle Methods in React

This project covered some amazing concepts that are fundamental to React. First remember that there are 3 Phases when we talk about Lifecycle methods that include:
1. Mounting = 
2. Updating = 
3. Unmounting = 

Each has certain methods/functions called before, after or during the phase.Soon, something called "Context API" could replace Redux. 

## Coding

The most difficult part of coding this application was having the data attributes from my has_many and belongs_to model relationships after the user filled out the form to show up on the orders made page. Finally, using debugger and adding the correct Active Record association methods in my create method as well as seeding my data after I had wiped it away made a huge difference. This project truly tested all my coding knowledge and pushed me to learn more than I ever have. My React debugging skills sharpened, as I helped classmates debug routing errors and understand why their state and props data were not rendering or working correctly. I am so proud of the progress I have made up to this point and hope to continue learning more each day as a professional software developer. 

## Shoutouts 

Firstly, I want to give thanks to my Almighty and Heavenly Father, Jesus. He really uplifted me throughout this project build and supported me when I wanted to give up or could not find a solution. I love you Jesus, thank you dad! I would not have gotten to this point without the powerful prayers of my family and friends. I am so thankful to my family for helping me get to the finish line. They encouraged me when I was stuck by rubber ducking with me and listening to my thought processing while I was talking out my coding errors. I am also grateful to my classmates and cohort lead for the endless support through this incredibly difficult but rewarding journey to my final portfolio project. Thank you Flatiron Coding School for an unforgettable journey and solid education you have provided me. 









---
layout: post
title:      "Riding on Rails and JavaScript Waves: Portfolio Project 4"
date:       2020-11-17 21:24:13 -0500
permalink:  riding_on_rails_and_javascript_waves_portfolio_project_4
---

![homehero](https://user-images.githubusercontent.com/61069416/99468969-ce75b180-290f-11eb-9088-759dd7545bcf.png)
## Planning Stages 

During the planning process for my Rails back-end and JavaScript front-end project I was overwhelmed. I did not know where to begin! I took the advice of my cohort lead and focused on building solid model relationships, mapping out my tables, attributes and controllers. I took a few days to sort out which has_many and belongs_to relationship I was going to pair with which model. I also learned how to build code "vertically" in order to reduce bugs and errors. This means do not build out all of your tables, attributes and files one right after the other but instead focus on building out one action method, one model relationship, make one fetch request and get back one JavaScript object in the console. This proved to be extremely effective and helped me realize that my project did not need the extra relationships and tables that I had originally planned out. 

Below were my original models for the project before I implemented the coding "vertically" strategy.
```
  
class Business
  has_many: :listings
  has_many:  :home_services, through: :listings
end
  
Class Listing
  belongs_to  :home_service
  belongs_to :businesses
end
  
class HomeService
    has_many :listings
    has_many :businesses, through: listings 
end 

```

Here is my final models after coding vertically. This meets the many to many relationship project requirements.

```
  
Class Listing
    belongs_to :home_service
end 
  
class HomeService
    has_many :listings
end 
```
## App Idea

Homehero was built from a personal experience. My parents own a small cleaning company that is family-owned and their hard work these last 10 years has been one of my greatest sources of inspiration. I see them pour their heart into their job and I too hope to put that much effort and love into all the work that I accomplish. Due to the recent global pandemic,  their cleaning company along with countless other small household businesses in our area, have seen their clientele and jobs reduce drastically.

My goal was to create a website that would bring together all the ad listings of small household businesses in the Washington D.C., Maryland and Virginia area in order to highlight all the amazing small business teams during this crisis. Many people are not sure which businesses are still open and what COVID-19 policies each company is making sure to implement during this time. Homehero does all the heavy lifting for you! Instead of endlessly googling and yelping which small household companies can help you repair your fridge, clean your home, paint your garage, fix your pool, change your pipes and more. Simply click on the "Listings" button to see all the listings in the DC Metro area. If you are a business, then you can easily create your own Listing by clicking on the "Create Listing" button which takes you to the Listing form. Here, you fill out your business name, ad name, write your ad message, write out your COVID-19 policies and choose the type of Home Service that your business offers. 


![Screen Shot 2020-11-17 at 9 01 57 PM](https://user-images.githubusercontent.com/61069416/99474465-a17acc00-291a-11eb-8894-1b908022ff35.png)

![Screen Shot 2020-11-17 at 9 07 23 PM](https://user-images.githubusercontent.com/61069416/99474470-a5a6e980-291a-11eb-84d9-e3bf60f09cdf.png)
## App Mission

Small Household Businesses to the Rescue! Homehero's mission is to reduce your countless internet searches and give you a one stop place to either list your small househould business ads or find small businesses that can help revamp your house! 

![Screen Shot 2020-11-17 at 9 22 38 PM](https://user-images.githubusercontent.com/61069416/99474687-0a624400-291b-11eb-8278-4a7519f8fbe5.png)


## Restful Routes and CRUD Actions
What exactly is REST? And why is it important? REST stands for Representation State Transfer. It is a set of conventions for structuring our routes and mapping them to CRUD action methods (Create, Read, Update, Delete). They are needed because without the CRUD action methods, our app would not be able to receive the get requests and send them to the corresponding action method names as they are fetched to the API. Below are all the Rest and CRUD actions found in my Listing model. In. the future, I plan to build out the edit and update methods for the user to be able to go back and change the listing form they originally submitted.


  | METHOD | ROUTE | CONTROLLER ACTION   | Description |
| ------------- |-------------| ----------- | ------------------- |
| GET  |  /listings | #index | Show all listings | 
| POST | /listings | #create | Create a new listing
| GET  | /listings/new | #new | Render form for creating a new listing|
| GET  | /listings/:id/edit | #edit | Render form for editing a listing  |
| GET  | /listings/:id | #show | Show a single listing |
| PATCH | /listings/:id | #update | Update a listing |
| DELETE | /listings/:id | #destroy | DELETE a listing |


## Coding
Coding this project was the most challenging but most rewarding out of all my projects. Up until this point, we have been using synchronous languages such as Ruby that are natively single threaded. This means the code is read top to bottom and can only do one thing at a time. Now, I could finally use AJAX and not have to constantly keep refreshing the browser in order to show my site. AJAX is a technique that gives users fast and engaging sites and helps us send and receive data quickly so that the user has a fast and smooth experience on our site. AJAX uses JS to add more to the DOM and uses fetch requests. We fetch data with fetch( ) requests to apply AJAX, in order to load the data after the information is presented to the user. A promise is the return object from a fetch request.  AJAX relies on promises, XML HTTP Request Objects, Event Loops, JSON (JS Object Notation) and Asynchronous ouput and input. Here are some diagrams that helped me understand these concepts better.

![scheme](https://user-images.githubusercontent.com/61069416/99472140-fff17b80-2915-11eb-90e0-fd9a56ec1d7a.jpg)
![Node js-Web-Application-Architecture-schema-7](https://user-images.githubusercontent.com/61069416/99472133-fd8f2180-2915-11eb-9048-0ef28a984db3.jpg)
![JS-generation-widgets-AJAX-web-application-architecture-schema-2](https://user-images.githubusercontent.com/61069416/99472130-fcf68b00-2915-11eb-811b-db88feec08be.jpg)


All the events appeared on my DOM instantly without a page refresh and this increased the probability of my user not deciding to click away from my website and stay engaged with the content and mouse clicks. This is because JavaScript is an asynchronous language, or a nonblock language that doesn't wait for a function to finish like a thread. JS processes every line as it reads it and not as it executes it. This was something that took me a while to wrap my head around but once it finally did, it made understanding how to code this project much more interesting!


## Scoping
Always ask yourself, what is our current situation? Meaning what is the access or rights that we have at any given time in this block of code. Remember that we can't change the scope. 

The three types of JS scopes are Global scopes, function scopes and block scopes. 
## JS DataTypes
1. Integers (1, 1.2, 2, 3.4 NaN)
2. Strings = “Timmy” or 'Please feed dog’ ,  backticks `${interpolate} `
--> backticks interpolated with $ = called Template literals
3. Null (null - empty, similar to `nil`)
4. Boolean (true, false)
5. Undefined = empty place holder 
 6. Object = { } , [ ],  function() 
 7. Function
 8. Array
 9. Symbol - new symbol ("name")
  

## 2 Types of JS Objects
The two types of JS Objects include the Primitives and the Complex Type of objects. The primitives consist of strings and booleans. The Complex Types include arrays and null.

## 10 Helpful Tips

1. Take a few days to strategically plan out how you want to build your app, it's all about the details here. Ask yourself, are these attributes or tables necessary for my project? Am I being considerate when naming my attributes and variable nodes in my DOM? They should have specific names that tell me what will be accomplished.
2. Take walks when you having been stuck on an error in order to come back refreshed and ready to finish!
3. Don't be shy to reach out to other classmates/ coders and start debugging zooms! I reached out to many of my classmates this time around and it really helped increase my debugging skills since you can learn so much from others then coding alone!
4. Don't try to over build, first make sure you have a functioning project that meets all the requirements before you go ahead and keep adding more styling or buttons. Think simple and then you can build off of your foundation!
5. Stay hopeful and keep a positive attitude. The greatest lesson I learned this time around was the power of the word "yet." I adopted a growth mindset, where I believe that as a student my abilities can only grow. And that I don't now how to do that yet but soon I will was the mentality I had during this project build.
6. Take the time to use mozilla documentation in order to boost your knowledge on how to use JavaScript methods or fetch requests.
7. Pray, pray and pray! Jesus always knows what you need and only He can give you rest!
8. Make sure you get enough sleep, exercise and a healthy diet. It's easy to neglect lifestyle habits when we are coding but it will be to our benefit.
9. Make a schedule of all the things you need to accomplish each day and stick to it!
10. Draw out how you want your project to look, specifically your web pages and how you want things to render on the DOM. This was very helpful to me as a I pieced together the front-end HTML and JavaScript code.

## Challenges
My biggest challenge arised when building out my select option drop down in my innerHTML for my Listing Form. This drop down included all my home services types. I could not understand why I kept getting nil back until I followed these steps. 



Here are the steps that helped me debug and get back an actual string of data:

```
 1. First make sure you run 'rake db:seed' just in case your data was wiped. This happened to me many times throughout the project when I had previously changed attribute names or dropped tables. 
 2.  Call your object, call save on your object if you are using .new active record method
 
[1] pry(#<ListingsController>)> listing
=> #<Listing:0x00007fd969144e30
 id: nil,
 ad_name: "BEST PRICES",
 business_name: "happy houses",
 add_message: nil,
 created_at: nil,
 updated_at: nil,
 homeservice_id: 0>
[2] pry(#<ListingsController>)> listing.save
=> false

3. Call errors on your object
[3] pry(#<ListingsController>)> listing.errors
=> #<ActiveModel::Errors:0x00007fd9691c3460
 @base=
  #<Listing:0x00007fd969144e30
   id: nil,
   ad_name: "BEST PRICES",
   business_name: "happy houses",
   logo_image_url: nil,
   location: nil,
   add_message: nil,
   add_image_url: nil,
   created_at: nil,
   updated_at: nil,
   homeservice_id: 0>,
 @details={:home_service=>[{:error=>:blank}], :business=>[{:error=>:blank}]},
 @messages={:home_service=>["must exist"], :business=>["must exist"]}>
 
 4.  Inspect your params and object_params
[4] pry(#<ListingsController>)> listing_params
=> <ActionController::Parameters {"ad_name"=>"BEST PRICES", "business_name"=>"happy houses", "homeservice_id"=>"Remodel"} permitted: true>

```



## Shoutouts 

Firstly, thank you Jesus who pulled me through the difficult valleys and nights when I was burnt out from coding. God was my constant rock and strength throughout this project and I owe this project all to Him! He helped me make a project that I know will help many small businesses during this pandemic! Thank you to my incredible family who supported me since day one of my Flatiron coding journey! My parents, my sisters Jean and Karol and my brother-in-law Grady were my constant support system. I am also indebted to my classmates who always inspire me to keep debugging and help me be a better coder. 

## Takeaways

This project has sparked and pushed my fascination with Javascript functions and methods. I plan to build on this project and add another Business model so that companies can be registered with the site. I want to build a way for users to leave reviews after a verified service was complete. I also want the user to be able to select the ads pertaining to the specific home service categories they are looking for through a button drop down in the html file and adding an onClick function in the index.js file. 



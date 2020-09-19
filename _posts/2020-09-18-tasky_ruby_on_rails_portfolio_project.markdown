---
layout: post
title:      "tasky: Ruby on Rails Portfolio Project "
date:       2020-09-18 19:35:32 -0400
permalink:  tasky_ruby_on_rails_portfolio_project
---


![taskylogo](https://user-images.githubusercontent.com/61069416/93532739-94882f00-f90f-11ea-91a3-932ca8595d23.png)

![tasky2](https://user-images.githubusercontent.com/61069416/93535003-1e39fb80-f914-11ea-8e65-522a3f3fd8f9.png)
## Idea for App

Tasky allows users to create, edit and delete customized daily tasks, daily routines and daily journals. Tasky's mission is to serve as a task management system for adults and children with ADD and ADHD (Attention-deficit/hyperactivity disorder) that struggle with managing their time and responsibilities. Tasky helps you thrive everyday of your life! The goal of this app is to provide an easy and user friendly experience paired with a sleek User Interface design that exceptionally helps people organize their priorities and find a calm balance in their daily lives. 

This is the **first ever online** ADD Task Management system that not only helps you prioritize your tasks and task deadlines but helps you track your ADD symptoms, medications, supplements and more. The Daily Journal feature helps you plan your spiritual, psychological, biological and social long-term goals. The user also has the ability to seamlessly create custom Daily Routines that gives you a visual flow and timeline of what you need to accomplish each day.

Let tasky take your day to infinity and beyond!


## Planning Stages
As someone with ADD who has struggled with finding balance with my time and tasks to accomplish each day, I wanted to create a web app that could quickly help me strategize and map out my responsibilities for each day as well as help me maximize my focus, productivity and efficiency. 

When planning how I would carry out each feature that I wanted tasky to include and deliver for my users, I started with brainstorming my relationships, attributes, creating my models and migrating my tables in my notebook. I then used this [this online mapping tool](http://app.diagrams.net/) to visualize each table and model relationship. For this Rails project and assessment, we were asked to include:

* At least one has_many relationship (x has_many y; e.g. User has_many Recipes) 
* At least one belongs_to relationship (x belongs_to y; e.g. Post belongs_to User)
* At least two has_many through relationships (x has_many y through z; e.g. Recipe has_many Items through Ingredients)
* At least one many-to-many relationship (x has_many y through z, y has_many x through z; e.g. Recipe has_many Items through Ingredients, Item has_many Recipes through Ingredients)
* The "through" part of the has_many through includes at least one user submittable attribute, that is to say, some attribute other than its foreign keys that can be submitted by the app's user (attribute_name e.g. ingredients.quantity)

This was my original attempt at mapping out my tables. 

![Screen Shot 2020-09-01 at 12 32 30 PM](https://user-images.githubusercontent.com/61069416/93636319-b6da8500-f9c1-11ea-8198-d3ebf95f55a5.png)

Understanding the many to many relationships requirement was one of the more challenging aspects of the entire project for me because I could not figure out how to best implement my joint table for the `has_many through association.` A **joint table** or joint model is a special table indirectly made by the **through** part of a has_many through association in the database. It helps join together a many to many relationship between two models and contains the two foreign keys from those two models. In the example below, the Comment model is my joint table and the two foreign keys included in this table are the user_id and task_id. My Comment model also includes at least one user submittable attribute, the message attribute, in addition the foreign keys that the user can submit such as: `comments.message`

### Joint Table & Has_many through Association 
![Screen Shot 2020-09-18 at 2 59 20 PM](https://user-images.githubusercontent.com/61069416/93635463-5139c900-f9c0-11ea-90e1-18603f153b97.png)
```
class User < ApplicationRecord
     has_many :comments
     has_many :commented_tasks, through: :comments, source: :tasks 
	end 

class Comment < ApplicationRecord
    belongs_to :user, optional: true 
    belongs_to :task, optional: true 
end

class Task < ApplicationRecord 
   has_many :comments, dependent: :destroy
   has_many :users, through: :comments
end 
``` 

My initial confusion with my tables and not being sure which attributes would best fit my project, led me to dedicate a lot of my valuable project time that I could have used elsewhere to creating new columns and new tables, renaming tables, changing datetypes, renaming columns and deleting columns. On a positive note, this did help me grow very comfortable with all the create migration and rails generate commands. A helpful tip here was that I found an easy way to change or add new columns/or new table names for tables in VS code. These are the easy steps: 

### How to Change/Add new columns or new table names 


1. Run `rake db:drop`
 ``` 
 rake db:drop
      =>  Dropped database 'db/development.sqlite3’
 ```
2. Manually delete sqlite file if not already deleted. 
```         
      =>  Database 'db/test.sqlite3' does not exist
```
3. Manually change/add new columns to the original tables that were created in the database files. You also have the option to use rails generate commands here to change/add new columns in the command terminal. Note, if you are going to replace names of exisiting tables, make sure to go back and change all corresponding controllers, models, views, forms, routes, ect., before you run the next command.
4. Run `rails db:migrate` 
5. You should see the new migrations created in your terminal. Check your schema.rb file to confirm that all your changes were saved to the database.
6. If you receive traceback errors in the terminal, run `rails db:migrate:status ` to point you to the root of your error.
```
rails db:migrate:status    
=>  database: db/development.sqlite3
```
                                                   
![Screen Shot 2020-09-18 at 8 41 54 PM](https://user-images.githubusercontent.com/61069416/93655078-6c6ffd00-f9ef-11ea-95e3-43438fa0a339.png)
In this example above, the error was refering to my `RenameVitaminsToSupplements` file where I had initially changed the attribute name of vitamins to supplements. Since I had already previously removed the supplements attribute from the table in Step 3, I had to delete this `RenameVitaminsToSupplements` file due to old attributes. This solved my terminal error.

` For traceback errors in the terminal: `
         * You may still have old attributes that you are no longer using somewhere in an existing file. Double check that you have deleted any old migrate rename files in your database folder where you no longer have those attributes you had initially renamed. If this is the case, delete that file. 
         * Double check that you have changed the name of your model/controller if you were replacing the name of a table.


### Rails Associations

I suggest that you give yourself a few days to read and take notes on the [Active Record Associations documentation](https://guides.rubyonrails.org/association_basics.html#the-has-many-through-association)  and take the time to fully comprehend the 6 different types of Rails associations and know how they are used. After understanding the fundamentals, now be confident when you choose what models relationships you will create from your tables. Make sure to print out or copy and paste all the rails project requirements in a seperate google doc so that you can easily refer back to it when making decisions for how to carry out your project. Another helpful tool that I used throughout this app build was the Mac [Quiver app](https://apps.apple.com/us/app/quiver-take-better-notes/id866773894?mt=12). It's a notetaking app that stores all your code and text based on whatever coding language (has over 120 languages) you are working with. I downloaded Quiver on my Mac in the app store. It is one of the best $10 investments I have made. Using the Quiver app made it easy to refer back to all my Ruby on rails notes from this module. 

Here are all my model associations I created for each class. 

```
class User < ApplicationRecord
     has_many :comments
     has_many :commented_tasks, through: :comments, source: :tasks #tasks they commented on 
     has_many :tasks #tasks that user has created 
     has_many :journals 
     has_many :daily_routines 
	end 

class Task < ApplicationRecord
   belongs_to :user, optional: true  
   has_many :comments, dependent: :destroy
   has_many :users, through: :comments
end

class Comment < ApplicationRecord
    belongs_to :user, optional: true 
    belongs_to :task, optional: true 
end


class Journal < ApplicationRecord
    belongs_to :user, optional: true 
    has_many :users
end

class DailyRoutine < ApplicationRecord
    belongs_to :user, optional: true 
    has_many :users
end
```

After studying the assocations and understanding the overall flow of my tasky app, this was my final diagram for my model relationships. Notice how different they are compared to my first attempt and how important it is to review the proper documentation before starting. 
![Screen Shot 2020-09-18 at 12 53 30 PM](https://user-images.githubusercontent.com/61069416/93635796-e63cc200-f9c0-11ea-8249-f5e93353729e.png)


## Coding


Three importants components of code to keep in mind when working with this framework is Models, Controllers and Views. The Model holds all your data and is responsible for the database. It is similar to a chef in a restaurant. The Model chef knows how many meals to make and know how to make a burger. The ActiveRecord framework gives us access to many methods outside of the rails framework. Your models should hold all your associations, custom methods and the be more thick than the controllers. The Controller is responsible for holding all the logic, web requests and holds all the action methods. The controller is like a waiter is needs to remember that it was table 7 that ordered the burger request. The Views are the presentation of your templates and what the app visually looks like to the user. It is responsible for HTML styling and can render partials (explained below in Partials section). 

The three main parts of the Rails framework are as follows:
* ActiveRecord
* ActionController
* ActionView = Made up of URL helpers
      
An example of dynamic URL helpers are the route helper methods. If we were to change up the routes, in many cases our code would not have to be altered at all because the route helpers are methods and not strings. Although, they cannot be used in our models. Below are some examples of how route helpers can be easy to read, very clean and simple code to add to our controllers and views. 
	
```
task_path(@task)
						 
or
						 
task_path(task, opt_in: true)
```
            
						
						
### Request and Response Flow
![Screen Shot 2020-09-18 at 4 13 15 PM](https://user-images.githubusercontent.com/61069416/93641230-f0af8980-f9c9-11ea-8152-2d2957820d79.png)
Now that my models were established, it was time to generate my controllers and define my routes. I hit a roadbloack with numerous routing errors for a few days and with grasping how my routes were connected to my server, forms and controllers. These two diagrams, located above and below, helped me better understand the cycle. First, the brower makes HTTP requests to webservers, and then loads the Rails router which searches for matching URLs. The rails app asks the router to match it to the corresponding controller action methods. We can also say that the specific request is sent to the controller's matching action method. The views are then rendered according to the view name that matches the correct controller name. 
![rails_routes](https://user-images.githubusercontent.com/61069416/93636854-9d860880-f9c2-11ea-81a2-8ada42365bea.png)

Here are some helpful notes to keep in mind with understanding GET and POST requests:

`Browser —> sends HTTP request —> to webservers` 

* **HTTP requests**  = have verbs

* **HTTP verbs**: `GET POST PUT PATCH DELETE` 
         —> describe nature of request 
				 
* **GET Request** = when your browser is asking for info

*  **POST Request** = when browser is giving info
        —>  I give you post request form data (ex: submitting a form) because it takes all the stuff you type in 
        —> And it sends form to web server 
				
If for instance, I have added a new user action in my users controller, when I hit enter the browser will make a request to the rails app. 
```
GET /register - new user action
``` 

The rails app then goes to the routes file and asks two questions:

  1. Should I respond to that URL?
  2. If so what method should I call in what controller?
         —> It's gonna say URL for register route 
				  —> And yes you should call new method in Users controller 


**4 Steps for Request Cycle:**

1. Browser makes a GET request to `http://localhost:3000/register `
2. Rails app now loaded the Rails router 
3. It found the match for requested URL
4. It directed the request to corresponding controller action
5. By going to `http://localhost:3000/register` we’ve allowed the user to trigger this new method code in Users controller.


### Generating Paths and URLs from Code

The Rails router job is to check and match URLs to the respective controller's action, or to a Rack application. A router can also make paths and URLs so we don't have to hardcode. For example in your routes config.rb file we could have:
```
get '/tasks/:id', to: 'tasks#show', as: 'task' 

```

In the Tasks controller: 
```
@task = Task.find(params[:id])
```

And in the Tasks view:
```
<%= button_to "Delete Task", task_path(@task), method: :delete, data: {confirm: "Are you sure you want to delete this task?"} %>
```

Next, the router makes this path `http://localhost:3000/tasks/1` which makes it much easier to read your code. 


The routes for your Rails app are always located in the config/routes.rb file. I learned that the `Rails.application.routes.draw do ... end` block found in this file cannot be deleted as it is necessary to form the scope for the router DSL. In my application, I utlized **Resource routing** which helps you establish your routes for the  `index, show, new, edit, create, update and destroy` actions in one line of code as opposed to seperate routes. My Resource routes can be seen below:

``` 
Rails.application.routes.draw do
 
  root to: 'application#index'
  devise_for :users, :controllers => {registrations: 'registrations', omniauth_callbacks: 'callbacks'}
  
  devise_scope :user do
    get 'login', to: 'devise/sessions#new'
    get 'signup', to: 'devise/registration#new'
    get '/users/sign_out', to: 'devise/sessions#destroy'
   end
   
  resources :comments
  resources :tasks
  resources :journals
  resources :daily_routines

resources :tasks do
  resources :comments, only: [:index, :new, :create, :show] 
end
  
  # For details on the DSL available within this file, see https://guides.rubyonrails.org/routing.html
end
```


### Scope Method Adventures

We were asked to create a custom scope method for this project. More specifically we needed a:
* Class level ActiveRecord scope method (model object & class method name and URL to see the working feature e.g. User.most_recipes URL: /users/most_recipes)

This was my favorite part of this project because it challenged me to think outside of the box and build something that was unique to tasky. It also served as an important feature that many tasky users will utilize on a daily basis so I wanted to make sure I did my research and fully understood how to use this amazing custom rails method. A scope method is a custom class method that gives you back active record associations or queries and helps make your code more dry. It also helps with organization and efficiency, since scope methods are chainable. When we call on a scope, ActiveRecord::Relation objects are returned not an array of elements. They can also receive parameters. Scopes are placed in the model and called on in the action method in your controller.

I created a scope method called `priority_order` that used the Active Record `order` method to sort all my tasks on a descending scale from 1-6. A user can rank their Daily Tasks from Highest to Lowest Priority. Where 6 is the highest priority and 1 is the lowest priority. 

```
class Task < ApplicationRecord
   scope :priority_order, -> { order(priority_ranking: :desc)}  
end


 class TasksController < ApplicationController
   def index 
        if user_signed_in?
            @tasks = Task.priority_order
        else 
            redirect_to '/'
         end 
    end
	end 
  ```

Below is my **task index view** displaying my scope method in action:

![Screen Shot 2020-09-17 at 8 43 11 PM](https://user-images.githubusercontent.com/61069416/93543713-4a607700-f92a-11ea-9d1c-781c22985df8.png)

### Nested Routes vs Nested Resources

For this section, we were asked to include:
  * Nested resource show or index (URL e.g. users/2/recipes)
  * Nested resource "new" form (URL e.g. recipes/1/ingredients/new)

A nested route is a route that is located inside of another route. The route to the left is called a parent resource and the one to the right side of the URL is called the child. We nest routes to keep track of the parent resource in the same URL. We may need the parent resource for some logic in our controller, and will not always want the user to have to provide it (e.g. via a form). The child resource is called exactly that because it is nested under the parent and this helps us make an easier to read URL for the user. In my project, you can navigate to one of my nested routes by typing `http://localhost:3000/tasks/1/comments/new ` into the URL. Here my parent resource is tasks and my child resource is comments. Below are all the nested routes created from adding the nested resources to my config.rb file.

![Screen Shot 2020-09-18 at 5 49 54 PM](https://user-images.githubusercontent.com/61069416/93647836-5eae7d80-f9d7-11ea-8a04-dc45372f281d.png)

Nested resources treat model objects as URLs are essential to using a resourceful style. Based on what your app needs, you can have multiple nested routes in your config.rb file that are many levels deep. For the purpose of this rails project, I only went one level deep. 
 
This is how I implemented the nested resources requirement for tasky in my config.rb file. 

```
resources :tasks do
  resources :comments, only: [:index, :new, :create, :show] 
end
```

Below is how I added the logic for the parent resource, tasks, and the child resource, comments in my controller. 

```

class TasksController < ApplicationController
     def show 
        if user_signed_in?
            set_task
            @comment = Comment.find_by_id(params[:id])
        else 
            redirect_to '/'
       end 
    end
		
		class CommentsController <  ApplicationController
		  def index 
         if user_signed_in?
            if params[:task_id] && @task = Task.find_by_id(params[:task_id])
                @comments = @task.comments
            else
                @comments = Comment.all
            end
        else 
            redirect_to '/'
        end 
     end
end 		
```
		

### Undefined Method Error
	
The last error that I ran into and was stuck on for a while was this NoMethodError in my DailyRoutines controller that said there was an undefined method "daily_routines" for the User object. To fix this error, I simply needed to make sure that I established the has_many association between user and daily_routines were a user has_many :daily_routines and a DailyRoutine has_many users. Somewhere between rearranging my associations, I had forgotten to add this essential association back. 

![Screen Shot 2020-09-17 at 8 14 43 PM](https://user-images.githubusercontent.com/61069416/93652914-c0291900-f9e4-11ea-98d9-1387efb74aa3.png)


```
class User < ApplicationRecord
    has_many :daily_routines
end 
```	
```
class DailyRoutine < ApplicationRecord
    has_many :users
end
```

### Create Tasks

Here you can map out your Daily tasks by clicking the Create Task button.

On this form, you can create a new daily task by filling out the task name and three actions to ensure the task is completed. A user is also asked to select the date the task was created as well as the deadline date. Lastly, you can choose the level of priority for that specific task.

![Screen Shot 2020-09-17 at 8 01 52 PM](https://user-images.githubusercontent.com/61069416/93544374-f22a7480-f92b-11ea-96f3-2cae66a4d591.png)
![Screen Shot 2020-09-17 at 8 00 30 PM](https://user-images.githubusercontent.com/61069416/93544416-09696200-f92c-11ea-86ea-ccb2bf8b57cb.png)
![Screen Shot 2020-09-17 at 8 00 42 PM](https://user-images.githubusercontent.com/61069416/93544399-02daea80-f92c-11ea-9e20-bf6414a83067.png)
![Screen Shot 2020-09-17 at 8 00 55 PM](https://user-images.githubusercontent.com/61069416/93544390-fd7da000-f92b-11ea-9880-94938232f094.png)
![Screen Shot 2020-09-17 at 9 37 16 PM](https://user-images.githubusercontent.com/61069416/93545257-f8215500-f92d-11ea-9529-4b9c7761d33e.png)
![Screen Shot 2020-09-17 at 8 10 01 PM](https://user-images.githubusercontent.com/61069416/93544287-b394ba00-f92b-11ea-8521-d6518d55a81a.png)
![Screen Shot 2020-09-17 at 8 06 15 PM](https://user-images.githubusercontent.com/61069416/93544326-c7402080-f92b-11ea-936c-7bb6a4fd3645.png)

### Create your Daily Routine

Plan your Daily Routine by clicking the Create Daily Routine button.

On this form, you can create a new daily routine based on what you want to accomplish by filling out all the sections listed.

![Screen Shot 2020-09-17 at 7 43 02 PM](https://user-images.githubusercontent.com/61069416/93539258-37e04080-f91e-11ea-8c5e-e382b694f6e6.png)
![Screen Shot 2020-09-17 at 7 43 39 PM](https://user-images.githubusercontent.com/61069416/93539246-31ea5f80-f91e-11ea-9ab1-de039a6ac882.png)
![Screen Shot 2020-09-17 at 7 48 31 PM](https://user-images.githubusercontent.com/61069416/93539429-c9e84900-f91e-11ea-8a54-746110f7b152.png)


### Create your Daily Journal

Here a user can track ADD symptoms, gain inspiration and create long-term goals in many areas of life. 

![Screen Shot 2020-09-17 at 8 10 30 PM](https://user-images.githubusercontent.com/61069416/93543973-e12d3380-f92a-11ea-96a8-d54faae819fb.png)
![Screen Shot 2020-09-17 at 8 10 39 PM](https://user-images.githubusercontent.com/61069416/93543954-d70b3500-f92a-11ea-8769-1e3153392d24.png)


### Create Comments

A user can create, edit and delete the comments they've posted on their tasks. They can also comment on tasks that belong to other tasky penguins in the community. 

![Screen Shot 2020-09-17 at 9 47 29 PM](https://user-images.githubusercontent.com/61069416/93545829-6b779680-f92f-11ea-982b-6931d5d55e2f.png)

![Screen Shot 2020-09-17 at 9 42 40 PM](https://user-images.githubusercontent.com/61069416/93545589-c8bf1800-f92e-11ea-955d-5f1f3e9e75bd.png)


### Tasky Penguins Community

 Tasky strives to help users build a supportive and friendly community of tasky penguins through our commenting feature. All users have the ability to comment on anyone's tasks to uplift, motivate and inspire other tasky penguins worldwide!  

![Screen Shot 2020-09-17 at 9 35 03 PM](https://user-images.githubusercontent.com/61069416/93545433-5ea67300-f92e-11ea-934d-298db1d1d7bd.png)


## 10 Helpful Tips

1. Each day I made multiple to-do lists that included goals that covered what exactly I needed to tackle that day. Including specific errors I needed to debug or questions I needed to ask my cohort lead and classmates. Every time I finished a task, I crossed it out. This helped me visually see all that I had left to accomplish.
2. Make multiple users, don't just use one to test out your project. Doing this, helped me identify various bugs, errors issues that were displayed from user to user in my views. 
3. Keep it simple, then create more models and attributes later. Focus on meeting the requirements first.
4. Save the styling until last. It can be tempting to spend time making your app look beautiful and internet worthy but it's not a helpful move if you are still degugging errors and completing the requirements. 
5. Make sure your user can create, edit, update and delete objects on each of your paths without a problem. Make sure all of your buttons are properly functioning.
6. Make sure you have whitelisted or permitted all your necessary attributes from your table into your **strong params**. Your strong params is needed in Active Model mass assignments when mass assigning data and is located after the private method you have defined towards the bottom of the Action Controller. It's important you are very careful when deciding which attributes will and will not be exposed to prevent any risk of showing attributes that you want to keep hidden by whitelisting the selected ones in the strong params. Below is how I implemented my strong params:

```
 private

    def task_params
        params.require(:task).permit(:date, :"date(2i)", :priority_ranking, :task_name, :action_one, :action_two, :action_three, :deadline, :estimate_time_to_finish_task, :user_id)
    end
```

7. Remember that **Model names** are **singular** and everything else (controllers, routes, views) is pluralized.
8. Take many walks and breaks from your computer to alleviate any back pain and eye strain.
9. Schedule time each morning to pray or medidate without fail. The more you give thanks to God for the opportunity to code and create amazing coding apps the more you will be at peace and can joyfully keep coding all day long. 
10. Clean and concise code, does not always mean better code. Make sure that if you are refactoring to reduce the quantity of code, that your methods can still be executed and that your overall app flow and routes are still functioning.

## Partials 
If it is appropriate to refactor, place the repeating code in a partial file in the respective folder in views. Partials are always labeled with an underscore at the beginning of the file. For example, my form partial created to reduce the repetitive code found in my comments edit and new views was named `_forms.html.erb` in the respective comments folder. This was the repeating code found in both my comments views: 

```
  <% if !@comment.task %>
    <%= f.label :task_name %>
     <%= f.collection_select :task_id, Task.all, :id, :task_name %>
     <% else %>
    <%= f.hidden_field :task_id %>
    <% end %>
<br>
<br>
     <%= f.label :message %>
     <%= f.text_area :message %>
<br>
<br>

    <%= f.submit "Save" %>
```
		
And this is how I referenced the partial in my comments edit view: 
		
```
<h2> Edit Comment. </h2>
		
<%= form_for(@comment) do |f| %>
    <%= render partial: 'comments/form', locals: {f: f} %>
<% end %>

```

My partial in my comments new view: 

```
<h2> Create a Comment. </h2>

<%= form_for @comment do |f| %>
     <%= render partial: 'comments/form', locals: {f: f} %>
<% end %>
```

## In the Future

In the next month, I hope to deploy tasky on Heroku, a free hosting site for web developers to showcase their projects. After that, I plan on purchasing and setting up a domain for tasky to be able to be used by adults and children who want to master their time and accomplish their goals. Stay informed about our lastest updates via [tasky's Github page](http://github.com/sandienunez/tasky). 

## Shoutouts
I want to thank my incredible family, including my wonderful parents and amazing sisters who supported me during this entire project build. They were amazing beta testers for my app and gave me incredibly useful advice in regards to design, product scale, marketing and user functionality. My family deserves a tony, grammy and an oscar for all the delicious meals they cooked for me, endless hugs, love and words of encouragement they showered on me. It would not have been possible without all of their help. They gave me the inspiration to keep pushing until the end and dared me to go above and beyond for this app.

A huge thanks to my cohort lead, Dominique, and my supportive classmates and the Flatiron School community of students. They helped me endlessly debug my errors and answer my countless questions until I understood the concepts. 

I am indebted to God's grace as He sustained me with his love, strength and heart during this entire journey. He led me beside still waters and casted away all my fears during this project. I am SO grateful for you Lord!

## Takeaways
 > Overall, this Rails application challenged me, pushed me farther then my limits and helped me grow as a software developer. 
  > It also made me fall more in love with the flexible nature of Ruby and how magical the world of Rails is. I am very proud of this project and hope that many people struggling with ADD can utilize all the powerful tasky features to help them dominate their day. 





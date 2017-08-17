---
layout: post
title:  "MVC Sinatra Application"
date:   2017-08-17 00:00:24 +0000
---


I am building a website for recipes using activerecord with sinatra.
The application will let user signup for an account to store and share their recipes.

The relationships between users, recipes and ingredients are as followed:
* User has many recipes, and a recipe belongs to an user.
* Recipe has many ingredients, through recipe_ingredient.
* Ingredients belong to many recipes, through recipe_ingredient.

The user table, recipe table, ingredient table, and recipe_ingredient table are created via migration, so the activerecord database schema can be altered easily.

Activerecord Validation is run upon creation of each object. It saves a lot of time when a good object model is set up. 

* User:
* * User must have an unique name and unique email.
* * User's name, email and password must present.
* * User has a secure password.

* Recipe:
* * Receipe must have a name
* * User's ID must present

* Ingredient:
* * Ingredient must have a name

The route and application configuration are implemented in the controllers,via RESTful route, which direct to various pages after verification. It has two helper functions: 
logged_in? - verify if user has the right to view member only pages. 
current_user - return the current user via session, so user cannot edit recipes by others. 

The controller will perform the CRUD (Create, Read, Update, Delete) actions using Active Record. 
The requested data are passed from the controller in global object, @user, or an array, @recipes,  to views.






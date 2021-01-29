---
layout: post
title:      "My Javascript Project - Cook Time"
date:       2021-01-29 05:39:56 +0000
permalink:  my_javascript_project_-_cook_time
---


Cooking is hard for me. I'm not a natural by any means. Anytime I cook, I have to use a recipe of some form and follow it closely. However, most of the recipe apps I use are kind of weird to use and are usually bloated by adds. They're just a bad experience for me. So, I decided to try my hand at creating my own! That's where Cook Time came in.

Overall, Cook Time is pretty simple, but I think that's what it makes it nice to use. You have recipes, which have some basic information, and each recipe has multiple steps. Steps have their own information as well. As you can probably guess, the relationships between these two models ended up being recipes have many steps, and a step belongs to a recipe. You might be thinking, 'what about the user model? Shouldn't users own or have many recipes?' ? I decided to go a different route and went with no users - all recipes and steps are open! Why? I wanted this app to be used by myself and my family really easy and we just didn't need a user model for that! In regards to the model attributes, I went with the following:

Recipes have:
* Name
* Description
* Ingredients
* Difficulty 

Step have:
* Name
* Description

I started implementing this functionality by generating new rails API project and writing rspec tests for my models (mostly testing validations) and rspect tests for the requests to my two controllers (RecipesController and StepsController). The request specs were written to test contoller responses in json format. Once those were written, I went ahead and made both the mdoels and controllers return that expected data in the format I wanted. To get the data to return in the serialized format I wanted, I used the FastJson API and passed it options for my desired format. Once I knew my data was coming out correctly, I went ahead and started writing out my JS. I won't go into too much detail here, but I created two different classes in my JS (Recipe and Step), used AJAX to fetch their data, and created instances from that AJAX data. From there, it was simply about getting those instances to display on the front end, in most cases.

All in all, this project was definitely a welcome challenge. Putting together a SPA makes me feel that much closer to being a well-rounded full stack developer. However, if or when I try to do another SPA, there are the things I would want to change:

* More intergration and E2E testing
* Using a non-RESTful style API, such as GraphQL, or something else
* Better Javascript file structure and an attempt at using Webpack

I definitely had a blast working on this and I'm excited for what comes next. Thanks for reading!


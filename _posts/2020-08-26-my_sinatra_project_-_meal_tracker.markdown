---
layout: post
title:      "My Sinatra Project - Meal Tracker"
date:       2020-08-27 03:44:41 +0000
permalink:  my_sinatra_project_-_meal_tracker
---


So, I'll be honest, I'm just starting to work out again and it sucks. Why does it suck? For me, it's the detail work that comes with getting really fit. You can't just workout and be really fit (for most of us). No, you have to workout, sleep well, stretch, and bribe the scale for better results. Even then, it won't get you there. The most important thing beyond working out is eating properly and tracking how and what you eat for your body style and workout regime. Doing that is a huge pain. There are a lot of apps out there that do this sort of thing. However, for my project, I wanted to put my own spin on tracking yours meals and their nutrional value. So that's what I did!

# What is it?
Simply put, users log into the website/application and create meals from items they have added. Items are anything you want to track with nutrional value, such as glass of milk or a salad. Meals are containers in a sense for a bunch of items. 

Each item has the following nutrional info to track:

* Calories
* Total Fat
* Cholesterol
* Sodium
* Total Carbs
* Protein

# How did I create it?
First, I started off with defining my models, which, as seen in my explanation above, turned out be meals, items, and users. From there, I figured out that I had to have some sort of join table between meals and items, which I decided was going to be called meal_items. After each model was created, I formed the relationships between them all, which can kind of be seen below:

* Users have many meals and items
* Items belong to users and have many meal items
* Meals belong to users and have many meal items
* Meal items blong to meals and items

After creating my models and their relationships, I then worked on mapping out my schema for those models. Once my schema was defined, I actually started working on a baseline UI/UX structure using layout.erb. Most of the structure was simple bootstrap base components and design. Once I had a decent starting point for UI/UX, I actually started creating the controller actions and views for my users, since they formed the base for meals and items. Nothing there was super difficult or tedious.

Once my users were up and runnning, I decided to work on baseline controller actions and views for both meals and items, but only with name parameter of their associated forms. I wanted to keep it simple and get everything working together before I tried to add the additional data for items and meals. Throughout this whole process, I experimented a bit with rspec testing! I'm not going to lie, it was a bit difficult and I ran into some troubles creating meaninful tests, but I think I'll get the hang of it more as I work on it.

After basic implementation of the items and meals were complete, I decided to move onto the actual meat of the data, which was the nutrional information. Integration of that was pretty easy for items, but it became a bit more difficult as I went to track the total nurtional information of a meal itself. It took awhile, but I finally managed to do so while keeping the logic DRY and clean in my Meal model. 

At this point, my app was pretty nearly in the MVP state, but I decided to spend a bit more time cleaning up the UI/UX, so everything was decently laid out, consistent, and not super duper ugly to the eye. That then became the submission of my project!
# What do I want to improve on this project?
* Right now, there is no way for a user to reset their password, as I didn't feel leaving comfortable leaving it in the my account page. That definitely needs to be added in future iteration.
* You can only select a checkbox to add an item to a meal, which doesn't representative a meal very well since you can have multiple quantities of something. I need to add some sort quantity selection going forward.
* If you have many items, it can become difficult to sort through or find them when adding to a meal given the current UI. I would love to add some sort of search functionality, or at least some sort of organization or pagination.
* Meals should be able to be organized by date and time so you can then add that additional level of tracking.

# What do I want to improve on future projects?
* More TDD! I did as much work with rspec as I could without going to much of a rabbit hole. I really want to intergrate as rspec more in future work.
* Removing some logic from controller actions. I feel like controller actions should be really lean and DRY and I want to carry that into my next applications.

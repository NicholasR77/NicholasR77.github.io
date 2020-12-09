---
layout: post
title:      "My Rails Project - Encounter Builder"
date:       2020-12-09 09:08:32 +0000
permalink:  my_rails_project_-_encounter_builder
---


I'm a nerd. I play video games, I read books, and watch weird, dorky films. Most importantly though, I play tabletop games ( If you don't know what a tabletop game is please look it up - you won't be dissapointed). My friends and I actually play Dungeons and Dragons every week or so and have done so for a few years now. Again, tabletop games are amazing, but, they are a bit tedious to keep track of and manage sometimes. There are a number of different solutions to this, but I really wanted to explore my own solution to managing my content for my D&D games. That's why I decided to create Encounter Builder.

Encounter Builder is, as the name suggest, about building encounters. What is an encounter? An encounter in most tabletop game is typically an event that takes place in a date and time between a number of different entities. This encounter could be fighting a dragon, to persuading a king, and much more. It's purposefully kind of a broad term since tabletop games are all theater of mind (mostly). When I considered at an encounter though, I wanted to break it down to some of the most common things associated with an encounter so I could form a basic start to this app. For now, I boiled my encounters down to interactions between player characters and non-player characters. Additionally, I decided to consider that player characters could bring unique items to an encounter, so I pulled that in as well. So that's what I ran with - my app was going to track encounters and the player characters, with their items, and non-player characters for each encounter.

To start, I formed a general schema of all of the relationships between notated models here. Now, part of this schema may seem strange, but I wanted everything to be able to be created on it's own and I wanted joins for pcs and npcs so they can belong to many different encounters. Here's what I came up with: 

* User - Has many encounters, has many items, has many pcs, has many npcs
* Encounters - Belongs to user, has many pcs through encounter pcs, has many npcs through encounter npcs 
* PCs - Belongs to user, has many encounter pcs, has many items
* NPCs - Belongs to user, has many encounter npcs
* Encounter Pc - Belongs to pc, belongs to encounter
* Encounter Npc - Belongs to npc, belongs to encounter
* Items - Belongs to user, belongs to pcs, nested to pcs (also unnested for standalone)

After creating that schema, I went ahead and began to write the general structure of the app. Nothing too crazy stands out here. I used partials and form_for to create several different forms for encounters, pcs, npcs, and items. I used collection select for both encounters via pcs and npcs and pcs via items. I setup my nested route for items, but also allowed it to be interacted with outside of the nesting with pcs. Also, I was able to implement OAuth for Facebook login and that is seemingly working out really well. All around, I had a great experience building this.

There are a few lessons and takeaways I've learned though:

1. Get good at TDD. I took a stab at TDD for this project, and it definitely increased the time and scope. Additional experience in this realm is exciting.
2. Helper methods are wonderful! Take advantage of them. They are great for keeping your code DRY and seperation of concerns.
3. In my opinion, focus on functionality over form at first. Get that prototype working. Red, green, refactor. I felt like I got stuck a bit in making my app pretty before I completed certain functionalties.
4. Before_action is freaking awesome. Use it more and more.

Again, I had a ton of fun with this project and I'm glad to get this one under my belt. Thanks for reading!



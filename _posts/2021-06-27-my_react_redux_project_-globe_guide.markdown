---
layout: post
title:      "My React/Redux Project -Globe Guide"
date:       2021-06-28 02:11:50 +0000
permalink:  my_react_redux_project_-globe_guide
---


I'm nearly at the end of the road and it feels weird. Programming has been difficult, there's no denying that. However, the difficulties and challenges have been well worth it. I've never felt more alive and have been more fufilled then I have over the last year. This final project was no different. 

I've always had trouble keeping things organized. It's difficult to remember all of the details of things and when they are and what they are about. Trips are extremely fun and can be awesome, but when you run into the challenges of organization, that's when it get's frustrating. That's where technology and, more specifically, Globe Guide came to mind. How can I make organizing your trips easier?

Globe Guide concepts are pretty simple - you have an account, your track trips, and then you track stuff within your trips. So when I went to create my models and strategize, I came up with the following:

* Users model - your account 
* Trip model - each individual trip, belongs to user
* Location model - the locations within a trip, belong to trip
* Cost model - the costs associated with a trip, belongs to trip

As I laid everything out, I began to realize how complex this app was going to be, so I actually decided to cut things down to just users and trips to start out with and for submission as my final projet. As such, I went to work. My Rails API was built with a users controller, trips controller, and sessions controller. Everything in the API simply returns some form of JSON back to the SPA. If the route is hit approriately, the JSON data will be returned via the JSON Serializer for the specific model/controller that is associated. I just used the fast_json API serializer which is easy to use and clean. 

One tricky thing I hit was authentication. How does your SPA know who a user is and if they are logged in? The solution I ended up coming up with is if the user is authenticated, my sessions controller passes JSON data about the user back to the SPA and the SPA stores that data in the users local storage for easy access and persistence. From there, everytime the main container of my SPA is mounted is checks to see if the user's JSON data is in the local storage, and if it is, uses it. If not, the SPA consider the user to be logged out. If the user wants to actually log out, we simply clear the local storage for the user. I think in the future I would definitely want to adjust this to some form of JWT instead though.

The SPA itself works pretty simply. I have 3 main container components: MainContainer, MainFooter, and MainHeader. MainFooter and MainHeader are as they sound, the footer and header of my site. They don't change during React Router adjustments. MainContainer is the foundational container and the base in which React Router swaps to whatever component it needs to display based on the route. In that foundational component, each routed component simply does its thing in terms of functionality - some are basic stateless components, while others are robust stateful components. Overall, though, my stateful component use Redux to handle tracking and adjustment of the global state when it comes to three different objects: trips, the current trip, and the current user. To generate these objects, Thunk is used in conjuction with Redux to make AJAX requests to my rails server and simply returns them. Nothing too special, but in retrospect, certainly challenging.

Overall, I had a ton of fun implementing this application and I'm really excited for the continued work I'm going to put into it. One thing I might adjust is the backend API I'm using though. I'm really excited to learn more about GraphQL and I think a React application like mine would benefit really from its use. Something to look forward to next!



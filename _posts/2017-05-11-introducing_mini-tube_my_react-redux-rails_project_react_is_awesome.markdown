---
layout: post
title:  Introducing Mini-Tube! My React-Redux-Rails project, (React is awesome).
date:   2017-05-11 17:51:50 -0400
---


This is a bittersweet Blog post. After months of hard work, I find myself at the end of the Flatiron curriculum. For every single day since I started in January, I've pushed myself to learn and code as much as I could with my free time. Truth be told, I didn't ever think about what it would feel like to actually be *done* with all the projects and the curriculum lessons. So, since I have no labs left to work on and Im feeling strangely liberated, I thought I'd begin my day today by writing about the React-Redux project I've put together after the last week, as well as the process of learning React in general.

Without further ado, here's a thumbnail of my project, a simple-youtube browser I called Mini-tube. You can also visit the site yourself at...  [Mini-tube!](https://mini-tube-client.herokuapp.com/ ) (hopefully nothing breaks too badly!)

![](http://i.imgur.com/KFmYbGZl.jpg?1)

In terms of functionality, the app is really simple - it queries the Youtube API for videos, lists videos using your search parameters, and lets users save videos to custom playlists (this data is persisted on the backend, with my seperately deployed Rails API-only server). The user authentication is custom rolled using JWT to generate unique auth tokens, and Jbuilder to serialize the JSON replies from my API routes. Though my app doesn't do all that much (certainly nothing that would compete with youtube), it was by far my most time-consuming project to date. Why, you might ask?

Well, for one, building a full-stack application using React usually entails having two seperate repos: One for your API and server, and another for your React-Redux front end. Essentially, this project broadly tests all your knowledge across the entire web stack - you need to have good rails fundamentals to put together your models, schema, and class methods on the backend. You need familiarity with a number of gems in order to implement user authentication. You need to have your Javascript down pat if you're gonna be making requests to APIs on your front end. And, the icing on the cake, you need to understand React-Redux in all it's glory if you want to pass assessment. 

That last bit is really the tough part. React-Redux throws nearly everything you know about MVC convention out the window. You're no longer designing views in your rails filetree. Instead, you're using the React library (alongside JSX, which is awesome) in order to *describe* how you want your pages to look. React then takes your instructions, and creates a super-fast website which only updates pages precisely as needed. Redux facilitates this process by saving your application state in something called a "store". The very idea of application state is alien to conventional application development - - so I'll spare you the details. Just know that it takes time to get comfortable working with React-Redux, and that if you're anything like me, you're going to feel very lost when you start off.

Ultimately though, React will let you develop an amazingly swift application, with really smart components. Every single thing rendered on a page can be its own component, with knowledge of the application state, of its own state, and the ability to shift or transform in response to User input:

![](http://i.imgur.com/xRNEeUPl.jpg)

Here's a super simple example from my project. This dropdown menu has little list items, and each item can be selected or deselected to add/remove a video from a playlist. Each time a list item is clicked, my React frontend is actually communicating with my database, and storing/removing that specific video from the playlist. Pretty neat. The dropdown is also an animated menu, which was another cool feature to add. It quickly becomes easy to see the creative freedom React gives you on the front end.

All in all, React is my favorite part of the curriculum so far. I really feel powerful with it - as if I could do or create anything I wanted using what I've learned. Though I've still got a long ways to go, I can say with confidence that you'll feel pretty amazing once you complete your React-Redux project (even if it's a dinky one like mine!) If anyone reading this finds themselves struggling with their project, feel free to reach out. I've got a lot more free time now that I'm done with all these labs!

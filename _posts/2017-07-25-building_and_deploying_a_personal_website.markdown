---
layout: post
title:  "Building (and deploying) A Personal Website!"
date:   2017-07-25 02:48:58 +0000
---


If you plan to work as a professional developer, one of the first things you should consider building is your own personal website! By creating a personal site, you can begin building your brand and marketing yourself to the world. In my experience, potential employers will react *really* well to this - after all, as professionals we definitely should have a place to showcase our portfolio and contact information.

That said, I just got done building and deploying version 1.0 of my portfolio site, and I'm excited to be able to share it with everyone! Here's the link: [My Portfolio Site!](http://mdjurdjevic.me/)

Though it's a little bare bones for now, I think I covered all the bases for the information I wanted to get in here!

I built the website as a Single-Page React application, since React is my front-end framework of choice. React's virtual dom works excellently for simple web-pages, causing all the different "routes" on my application to load instantly. The styling is done using semantic-ui and a few custom-built CSS transition animations. 

## CSS transitions
These are a whole lot of fun to play with! You might notice that there's a subtle fade-in effect as you swap pages on the website. I always thought fade-ins were pretty classy, so I added this effect to all the initial page loads (and that little nav arrow on the left of each page). The code for doing something like this is simple; you specify an animation on an element in your html (in my case, the entire viewpage was wrapped with a fade-in animation), and then you write the keyframes code for your animation: 

```
div#navarrowleft .text{
  position: relative;
  top: -18px;
  left: -10px;
  animation: fontappear 2s;
}

@keyframes fontappear {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}
```

This is a simple animation (I've named it 'fontappear') which transitions the opacity of text over a 2 second window. You might also notice that the little hamburger icon on the top right causes a more complicated full-page animation, which took quite a while to get right. Just remember that some CSS transitions & animations can be taxing for older browsers, so you want to primarily use simple, computationally-cheap transitions. Here's a great article if you want to read more about animation performance: https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/

## Filling In Some Content

As you can see, my site is rather bare bones at the moment - but it covers most of the bases I eventually want to have up here. I'd say the most important things you're gonna want on your portfolio page will be, of course, your work history and projects. I've added several of mine here, and will certainly be adding more as I continue building things. I'm in the process of deploying a bunch of my old projects - but, in the meantime, I've got links to youtube videos where I narrate through my code.

Another thing you may want to consider is some information about yourself, and a few ways you can be contacted. My personal about page isn't too robust just yet, but I've got some plans to add things that'll spice it up going forward!

## A Brief Note on Viewports

Since your website is going to be a display of your design prowess, you're definitely going to want to examine how your layout holds up across several different viewport sizes. It should, at the very least, be functional on mobile screen sizes. Sadly, I've got some ways to go as far as getting everything looking pretty on mobile, but I've added several media queries and breakpoints to make the app tolerable on both mobile/tablet screens. Still a work in progress, but definitely something to watch out for.

## Deployment!

Once you've got everything wrapped up nicely, you're ready to deploy your website! I used heroku since I've got an account with them and really like their extensive debugging/logging tools, but really you can use any hosting service you like. Purchase a domain name from namecheap/godaddy/whatever gives you the best rates, link it up with your deployed codebase and you're ready to go!


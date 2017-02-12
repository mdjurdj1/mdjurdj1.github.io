---
layout: post
title:  "So I Published an App!"
date:   2017-02-12 02:50:40 +0000
---


Today is a good day; I've finished building my very first app - Gameday - which is also a published Ruby gem! It uses nokogiri/openuri to scrape together a list of today's major sporting events, along with short articles about those games (when they're available). If you're so inclined, you can simply type: `gem install gameday_cli_gem` in your terminal to get the latest version of my app. The idea that anyone can now download and run the program I built is still mind-blowing, so you'll have to bear with my cheesy exuberance. 

However... shameless self-promotion isn't why I'm here today! Instead, let's talk a bit about my experiences developing an app from scratch for the first time:

* **Coming up with an idea**

![](http://imgur.com/a/0bXuO)

Make no mistake, this is going to be where you spend at least half of your total development time. It's hard enough to get started on a work assignment when you know exactly what's expected of you... creating something completely from scratch with absolutely no direction? Yeah - this is a procrastinator's nightmare. I suggest starting with a topic you're passionate about, or.. just make something you want to use yourself. I'm not a big sports fan persay, but most of my other friends are - and I often don't have the time to keep up with all the games going on. What's a guy to do? I came up with an app that could be used as a quick reference for all of the days' major games. Now, I can consult my app, get a summary of what happened, and not feel so out of the loop when I talk to my friends who have too much free time (heh).

* **Start typing out the code you wish you had**

I'm shamelessly requoting Avi here - but it's a pretty damned good tip. Just by writing a bunch of nonsense code in my once-empty program, I felt like I was making progress towards something. I no longer had to stare at a bunch of completely empty pages. I also had a rough outline of what I wanted my code to do. Developing code out of plainly written, understandable directions is much simpler than trying to convert your thoughts into code as you go along. It'll also help get the wheels turning if you're desperately procrastinating. 

* **Oh God CSS/HTML Scraping**

Scraping is hard. About 90% of my issues while developing my app had to do with the fact that my source page dynamically updates its css to display or hide content as needed. For example, the css classes for a finished game would magically dissappear if none of the games on the page were finished. Not only that, but some of the css classes were used to relay multiple types of information! This means that any selectors I used during scraping had to be extremely precise, and I needed extra code to account for all the optional css selectors I needed in order to distinguish finished games from upcoming ones.

Flawless scraping was made even more important because of the fact that my game objects depended entirely on scraped parameters for instantiation. Here's just a small portion of my custom game constructor, which takes an XML file from the scraper class, and converts it into a game object:
  ```
	if game.css(".game-link").text == "Preview"  
      self.new(
        game.css("div.media-body")[0].css("span").text,
        game.css("div.media-body")[1].css("span").text,
        game.attribute("data-league").text.upcase,
        game.css(".status-pregame").text.gsub(" ", "").gsub(/\n/, ""),
         "http://www.si.com#{game.css(".game-link").attribute("href").text}" )
				```
As you can see, every single parameter for my game object here is scraped. If any of the scraped code within the initialized arguments is off, my code defaults to a "nil" assignment for that argument. I spent a lot of time just getting this constructor to properly instantiate a single game, much less coming up with conditionals to account for games which didn't have reviews, games which were ongoing, finished, etc. Still, when I finally got that first list of properly reported games, it made all the scrawling worth it.

* **Publishing my work!**

Learn from my mistake - don't publish your scraping program the same night you feel it's finished. I did just that last night - I was so confident that everything was working that I pushed version 0.1.0 of Gameday right up to Ruby gems and went to bed. When I woke up and ran my app... Half of everything was broken. See, scraping is funny like that - you really need to know the ins and outs of a website, especially if the website is dynamically updated. You need to know what code is changing every day to account for the new information, and your program has to roll with the punches accordingly.

Test your program many times over several to make sure it works as the site is updated!!

Rest assured, after the initial panic of everything being broken, I got back to work on my code and released a patch which significantly improved Gameday's ability to react to its source website. I anticipate that things might yet break in the future, but that's life! All in all, I'm immensely proud of this thing I've created. It's a (very) small step to write a simple program like this one, but I can say that I'm no longer only a student of programming; I'm also a creator. 







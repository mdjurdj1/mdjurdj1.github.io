---
layout: post
title:  "Thinking Like a Computer [Code Troubleshooting 101]"
date:   2017-02-09 18:10:10 -0500
---


![](http://img01.deviantart.net/bef0/i/2016/319/f/b/thinking_like_a_computer_by_minadavic-daojjsp.png)
*Source: "Adorkadorks" by Minadavic. Link at bottom of page!*

Over the past several weeks, I've spent a few hundred hours trying to grow my programming skillset. When I started, I had little-to-no coding experience. I think I wrote a tiny Java program in middle school comp sci class once (spoiler: it didn't work). So, like many programming newbies, I've gotten stuck many, many times on coding solutions for seemingly simple problems. I cannot count the amount of times I've stared at a method three to four times long and thought to myself: *"Why the hell isn't this thing working like I want it to?"* Off the top of my head, I can think of several specific coding concepts which repeatedly stumped me:

* Why is this iterator loop not doing what I want it to do?
* Why doesn't this if/else statement trigger like I expect it to?
* My and/or statements are always broken! Why isn't it evaluating the entire line?
* Why are you returning an array/string, I just wanted an integer!
* Working with hashes is confusing, my brain hurts.

Unsurprisingly, I see a lot of other beginners fumbling through these same issues with their code. On a fundamental level, all these concepts are difficult for the same reason:

**We, as humans, do not think the same way computers do.**

The good news is: the longer you spend coding, the more fluent you become in computer-thinking. In reality, computer-think is suprisingly simple - computers take everything you type one-hundred-percent literally. They read from top to bottom, and left to right. They immediately forget things unless they're told to remember them. There aren't very many quirks to the expected behavior of your computer (well, the language you code in might have a few nuances). So, the next time you get stuck on a problem, try to think like your computer:

1. Go through your problem code one line at a time. 
2. Follow the computer logic for each line. If another method is being called in that line, go to that method immediately as a computer would.
3. Throw each line, individually, in an IRB session to make sure your logic for that one line is solid. 
4. With every line of code, check the class and return value of every single variable you come across, every time you come across them. You might be surprised to find a variable returning a value you don't want!
5. If you have conditional statements, you're gonna want to check the true/false value of your conditions as you come across them, one at a time.
6. Narrow down your problematic code blocks into the single lines of code that are breaking your program. Take note of the issue you're having - is it something you struggle with a lot? If so, it's definitely worth trying to deepen your understanding of that concept.

A lot of times, breaking down a problem line-by-line as a computer would do will give you a lot of insight into why your program isn't behaving as you expect. More than anything, it's helped me learn to think as a computer would - one line at a time - in order to troubleshoot my various errors. 

Hashes still kinda suck, though.


_____________________________________

Adorkadorks Comic: https://tapastic.com/series/Adorkadorks



---
layout: post
title: "The Power of Javascript"
date: 2013-07-28 10:02
categories: webdev
tagline: "will javascript become the most powerful language?"
tags: [javascript]
---

Week 6, Javascript week. After this week we are half way through the program, and what bugs me the most is that I still want to learn a ton of things in this short period of time. I want to be good at JS and write elegant scripts in Coffeescript, and I want to get familiar with Ajax to make requests, and ... and.

I have learned the basics of JS before, but I totally forgot what it is like. I am able to perform a few click and fadeIn effects in jQuery, and that's all I can do. This time I'm starting from scratch and with the Ruby knowledge, I get familiar with JS in a fairly reasonable speed. I am starting to see bits in this uglier language (compared to Ruby), and how pieces come together. One lab I did over the past 2 days was a Hangman game wrote in Javascript (no jQuery yet), and I utilized the <a href="http://underscorejs.org/" target="_blank">Underscore library</a> to simplify codes and <a href="http://raphaeljs.com/" target="_blank">Raphael library</a> to draw. With the two amazing libraries, I finished the Hangman Challenge with satisfaction! <a href="http://kevoncheung.com/anecdotes/hangman/" target="_blank">You can visit the game here!</a> Lets talk about challenges of this game and what I learned from it.

1) The Logic Flow: To create a game that is user-friendly, I've to think about the flow carefully about what functions to write and where they belong. For example, I need a makeGuess function as well as checkLetter, checkWin, checkLose etc. By the end of the game, I have about 20 functions that each perform different task, and some of them are connected to each other. I definitely recommend listing out all the functions to build a structure of the entire game first, and then go into each function and write the code.

2) Debugging: I forgot how many times I bumped into errors and got stuck in the process of writing this game (because there are too many), and I've seen other coursemates got stuck in the logic loop and did not know what to do. A practice of mine helps a ton, and everytime I see errors popping out of my console, I'm excited more than confused, because errors are the best in guiding me through to solve the problems! You will know its worse to have no errors popping out but your game is not working. This practice is nothing special, but it does save me time and lead me step by step to the finish line. After writing specific functions out, I tend to drop a console.log in the window.onload script and let it prints out results everytime I load the page. If its an anonymous function, let it run; if it takes parameter, place in a suitable argument for now and revisit later. As it goes on, I will have all the things I want printed out in console neatly, and I would know what to do next.

A very important point I would like to stress is don't be offended by writing a function that you have no idea would perform. A coursemate of mine had a question another day, he was confused why we couldn't just write big chunk of code in sequence, instead we went through trouble writing functions that take in a parameter (but we have no idea what parameter will get passed in). He is lost because without a specific set of data to get processed, it is hard to write functions. In fact, when you write functions, you should just imagine what kind of parameter should go in, and place data or variable that fit the function in your mind temporarily. Say you are writing up a function to make guesses for Hangman, you are likely to have 

	makeGuess = function(guessedLetter) {...}

, what does guessedLetter mean? You will never know because it is a "user input"! But for now, you can just imagine it is the letter "a". After you finish coding it up, console.log(makeGuess("a")) to see what comes out. Bingo. Move on to the next challenge.
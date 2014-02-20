---
layout: post
title: "Debate over Use of Bootstrap"
date: 2013-07-02 19:58
categories: webdev
tagline: "don't be best friend with bootstrap"
tags: [wdi, advice]
---

On Day 1 of Week 3, the course started introducing styling with CSS, and it definitely turns all of my programs appealing. With previous experience handling CSS, I jumped into using Bootstrap to style my simple program. Some course mates debate that using external resources is not "your own work", but I have a different perspective towards using external stylesheets.

In my point of view, hand styling for our course material serves as a practice for a lot of the students who just get introduced to the world of CSS. They need to understand the elements such as div, span, headings, paragraphs etc. For me, these tiny class assignment programs are better off using Bootstrap to reduce production time because not many people will get to see the product. Once it gets to final projects or websites that get to the eyes of audience, hand styling and customization are required. I'll even consider using Bootstrap for my personal website, as long as enough customization is carried out.

Another note I want to make here is I've been trying to set a background image on div, but after dozens of attempt in different applications, I still fail to display an image at the background. Color works though, and that is weird. Furthermore, I'm definitely not a master in CSS, I am looking forward to pick up more CSS3 tricks including transition, animations, and effects. CSS3 surely replaces a lot of jobs that previously need to be done with jQuery and it's just fascinating.

Transition is one of my favorites, and here is one example:

	#id {
	 -webkit-transition: all 0.2s ease-in-out;
	 -moz-transition: all 0.2s ease-in-out;
	 -o-transition: all 0.2s ease-in-out;
	transition: all 0.2s ease-in-out;
	}

Another interesting CSS to target just external links:

	a[href^="http"] {
	style all you want;
	}

You might wonder, what? The same animation takes up four lines of the same code? You're right. That's because it caters to different browsers. Webkit is the browser engine used by Chrome and Safari, Mozilla is used by Firefox, -o is for Opera, and sometimes you see -ms which is for Internet Explorer. In the future, when you want to use border radius or effects, remember to serve all your audience with different browsers well :)
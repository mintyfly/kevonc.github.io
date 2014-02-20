---
layout: post
title: "Project Kick with Data Visualization"
date: 2013-08-13 08:15
categories: webdev projects
tagline: "the world is overwhelmed with data to do more powerful things"
tags: [kickstarter, data visualization, wdi]
---

Ever since I'm exposed to two projects built by WDI alumni Larry Buchanan, I was determined to have a second project based on Data Visualization. What it means is extracting an enormous lot of data from somewhere, analyze them, and display the data in a way that an everyday person could understand. Great, the next step, the most difficult indeed, was to find the data. My partner Alina and I started out looking for datasets everywhere, and it was not an easy task. The data has to be formatted in a not-so-ugly way, and it has to be somewhat interesting. We began our project by researching on how to use <a href="http://datamine.mta.info/" target="_blank">New York MTA API</a>, but the General Transit Feed Specification (GTFS) was a little too much to take on at that moment, so we set out to work on another very exciting idea about <a href="http://www.kickstarter.com/" target="_blank">Kickstarter.com</a>.

Kickstarter only has a private API, whereas other crowd funding site like <a href="https://www.crowdtilt.com/learn/developers" target="_blank">Crowdtilt</a> offers a public API. However, we were only interested in the crowd funding giant and would not give up just because they don't have an API. Scraping immediately came to our mind, and I literally spent the whole weekend writing up a quite-heavy rake task to scrape Kickstarter.com with Mechanize. The scraping part was not difficult, as Kickstarter provides metadata that is very recognizable DOM elements to Mechanize. The tough part was figuring out the actual URL i should tell Mechanize to do the job, as Kickstarter uses AJAX request to pull in data when a user scroll down, so HTML only displays the first 15 projects, not the ones that come in by AJAX. Here's the trick, simple as it seems, pagination is a must have on many websites, so I simply placed a page number at the end of the url and all the pages are in front of my eyes immediately.

After scraping, another major task of ours was to analyze and display the data. We had spent more time working with D3 to display the data as it was our first time playing with it, thus we need to learn from scratch in a very short period of time. Therefore, our data analysis part was not very extensive but that's a way to improve in the future. Working with D3 was harder than I thought, not only do I need a good Javascript foundation, but it was a nice (weird) concept to learn. The way D3 works is that you have to select elements that are not there yet, by doing so, you're telling the program "Hey, my friends are not here yet, but let me reserve some seats for them!" A few articles about D3 that really got me off the ground are listed at the end of this blog post. I strongly recommend spending some time reading about D3, looking at what other developers did with it, and then play with it by creating simple rectangles and circles.

Those are the two main components of Project Kick (<a href="http://projectkick.us" target="_blank">projectkick.us</a>), and now is lesson time! After we had our rake task to scrape the entire Kickstarter site, we had a database filled with raw data, and they are not directly useful to D3 because it is best for D3 when the entire dataset is formatted nicely. The challenge we faced was turning the raw data into an useful set of data specifically for D3, and so we had to write another rake task to populate extra tables for formatted data. My recommendation on that is to do it the other way around, figured out what data is needed in D3's standpoint, and extract data based on that. Of course, we only had a week of time to actually learn so many new things, so we wouldn't be able to accomplish that.


Looking at the code now, there are a ton of rooms for improvement. Nevertheless, I'm extremely happy and proud of the project given the production time of one week. I'm excited to show this to everyone and even people at Kickstarter! I slowly come to realize that I enjoy front-end work more, and it is a good sign that I've figured out! On a side note, my personal website <a href="http://kevoncheung.com" target="_blank">kevoncheung.com</a> has finally come to life. It is very simple but good enough at this point as version 1.0.


<strong>Appendices</strong><br>
Larry Buchanan's Projects<br>
<a href="http://www.newyorker.com/sandbox/business/citi-bike.html" target="_blank">http://www.newyorker.com/sandbox/business/citi-bike.html</a><br>
<a href="http://www.newyorker.com/sandbox/business/ncaa.html" target="_blank">http://www.newyorker.com/sandbox/business/ncaa.html</a><br>

D3<br>
<a href="http://mbostock.github.io/d3/tutorial/bar-2.html" target="_blank">http://mbostock.github.io/d3/tutorial/bar-2.html</a><br>
<a href="http://bost.ocks.org/mike/join/" target="_blank">http://bost.ocks.org/mike/join/</a><br>
<a href="http://thecodingtutorials.blogspot.com/2012/07/introduction-to-d3.html" target="_blank">http://thecodingtutorials.blogspot.com/2012/07/introduction-to-d3.html</a><br>
<a href="http://www.fascinatedwithsoftware.com/blog/post/2012/09/01/Visualizing-Data-with-D3.aspx" target="_blank">http://www.fascinatedwithsoftware.com/blog/post/2012/09/01/Visualizing-Data-with-D3.aspx</a>
---
layout: post
title: "More Ruby Bits &amp; First Lab"
date: 2013-06-20 19:55
categories: webdev
tags: [wdi, ruby]
---

We continued to explore more ruby basics, introducing function, array, hash, and block. They are pretty simple bits to use when writing a program, yet the difficult part is understand how you can use them efficiently. To do that, one has to learn the list of methods associated, for instance, creating an array is no-hard task, but what can we do with an array? Select, reject, flatten, inject, uniq, shuffle, sample....... so many methods that it will take some time to digest! We haven't done inject in class today, but from my research, it is a more complicated method yet truly rewarding! A simple task it could do is add up the numbers in array by simply injecting (0). I'm also amazed what inject can do, say if we want to convert keys to be strings and change names to be lowercase:

	hash = [[:first_name, 'Kevon'], [:last_name, 'Cheung']].inject({}) do |result, element|
	  result[element.first.to_s] = element.last.downcase
	  result
	end

	hash # => {"first_name"=>"kevon", "last_name"=>"cheung"}

Beautiful, isn't it?

Day 3 also featured a lab exercise in which students in our WDI class should be randomly assigned to groups, and the size of the group is determined by an user input. Our task is to write a program that solves the problem. After about 10 minutes, my partner Beryl and I were able to figure out a way to solve the problem, a way we believed was quite smart. We used "times" "shuffle" and "shift" in our program to perform the computation, simply just shuffle an array of students and "puts" a group of student then cutting them off the array. And the best part came, I went over to check out some of our coursemates' code, they approached the problem in a completely different way by using "while" and "slice", interesting I think, programming really has no limits! The same problem can be solved in so many ways depending of each person's logic process. Some people walk the conventional way, some do a shortcut. Magic, this is magic. And I love this magic. Check out the exercise here.

Coming into the course with preparation, I still pick up a lot of new knowledge from instructors and other students. The lectures are great, but I have to say labs and projects are the main reason why I'm here today. I want to train my logic thinking process, perform pair programming, and work in a team environment. That's what self-teaching lacks.
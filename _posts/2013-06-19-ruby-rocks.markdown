---
layout: post
title: "Ruby Rocks"
date: 2013-06-19 19:54
categories: webdev
tags: [wdi, ruby]
---

Second day of WDI was all about Ruby, we learned how to use "pry" to perform ruby computation, and we wrote code to build a simple calculator.

The bits of ruby come in handy with prior self-teaching experience, but it's still nice to refresh my memory and gain new knowledge. One essential lesson from yesterday was when a function is defined, parameters can be return at the end for use later on. For example:

	def ask_for_numbers()
	  puts "What is the first number?"
	  first = gets.chomp.to_i
	  puts "What is the second number?"
	  second = gets.chomp.to_i
	  return first, second
	end

User is asked to input two numbers, and the function returns both numbers at the end. Later on when a computation is about to happen, the two numbers can be grabbed to use by "number_one, number_two = ask_for_numbers". This is interesting because instead of using instance variables, now the two numbers can be used in association with other functions, so it is not limiting itself to just one function, but multiples.

Instructor David also dropped by to introduce me to testing with rspec. As Test-Driven Development (TDD) is getting in the way nowadays, it becomes a more ideal way to write code. I have previously touched upon rspec from Michael Hartl's tutorial, and that tutorial was godly, it introduced so many elements in a Ruby on Rails application that becomes so useful when I start diving in deeper. In the following days, while we keep on learning the basics of Ruby and Rails. I'll want to explore rspec a bit more.

It has only been two days and every student is already coding intensely in class, I'm thrilled to discuss some potential project ideas with classmates today.
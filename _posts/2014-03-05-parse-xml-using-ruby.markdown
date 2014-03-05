---
layout: post
title: "Parse XML using Ruby"
date: 2014-03-05 21:43
category: webdev
tagline: ""
tags: []
---

To be honest, I've only worked with JSON in terms of handling data files. I was surfing some open data online, and came across XML, so I thought I would spend a bit of time teaching myself how to parse the data file using Ruby.

It is extremely easy to learn using irb, which stands for Interactive Ruby Shell.

First, load up irb in your command line
  wtf

In irb, we're going to use REXML, a pure Ruby XML processor.
  require 'net/http'
  require 'rexml/document'
  include REXML

Set the url to the XML file you find online, here we're going to use a simple one from W3
  url = 'http://www.w3schools.com/xml/simple.xml'

Turn the url into a readable XML format
  xml_data = Net::HTTP.get_response(URI.parse(url)).body

Set the root, which is the first layer of tag
  root = doc.root

Now when you should be able to list each element out
  root.each_element {|food| puts food }

To grab a specific one
  root.elements[1]
  root.elements[4]

To get just the name of each breakfast item
  root.each_element {|food| puts food.elements["name"] }

Now you might notice, the responses are wrapped in name tag, how do you get rid of it?
  root.each_element {|food| puts food.elements["name"].text }
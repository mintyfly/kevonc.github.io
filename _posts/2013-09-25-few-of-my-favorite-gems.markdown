---
layout: post
title: "Few of My Favorite Gems"
date: 2013-09-25 15:37
categories: webdev
tagline: "gem is your best friend in ruby development"
tags: [ruby, gem]
---

It has been awhile since I last wrote a blog post. After WDI that ended early Sept, I have been exploring different opportunities and working on a project. It was a project that I was trying to do before taking WDI, and back then it would take me a lot of time to figure out one small function (because I would have no idea where to start). Now, I am able to put together the core functions relatively quick, and use more time fixing details and enhancing the app.

For the project, I used multiple gems to support the development, which included devise, omniauth, simple form, carrierwave, friendly_id, rabl, kaminari, active admin and fog. I wanted to talk about a few of them specifically.

<a href="https://github.com/nesquena/rabl" target="_blank">Rabl</a> is a popular gem for generating JSON, XML etc. The idea is to customize JSON representation when ActiveRecord "to_json" method does not provide the exact JSON you want. In my project, I have a class (say Book) that connects to multiple join tables (say Authors) , and if I get a json from the Book controller, the json does not return the authors of the book because it is stored in another table. I need the JSON to include the authors to perform specific JavaScript function.

Here is one way to do it - Telling the controller to render JSON that includes associated records.

{% highlight ruby %}
class BooksController < ApplicationController
  def index
    @books = Book.order("created_at desc")
    respond_to do |format|
      format.json do
        render :json => @books.to_json(:include => { :author => { :only => :firstname } })
      end
    end
  end
end
{% endhighlight %}

But, the structure of the JSON is set in this case, which has a lot of layers (book.author.firstname). And I want it to format in a different way. To do that, I need Rabl to come to rescue.

{% highlight ruby %}
attributes :name, :price

node do |book|
  { :author => book.author.firstname }
end
{% endhighlight %}

This way, you can construct a JSON with three keys (name, price, and author), and calling (book.author) will directly give you the first name of the author. It is quite a hack.

<a href="https://github.com/norman/friendly_id" target="_blank">Friendly ID</a> is particularly useful because most of the time, we would want the url to reprensent more meaningful subject (say the name of the book). It is not ideal to have the id in the url, such as localhost:3000/books/1. It is confusing. Using Friendly ID, you just need to add a column to your book table :slug. The slug will generated based on the name of the book and the url will become localhost:3000/books/harry-potter. Much cleaner right?

Every project I learn something new, which gem did you use recently? Share with me!
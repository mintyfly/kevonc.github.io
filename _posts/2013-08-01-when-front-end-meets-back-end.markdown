---
layout: post
title: "When Front-End Meets Back-End"
date: 2013-08-01 23:08
categories: webdev
tags: [ajax]
---

I was extraordinarily joyful today, mainly because I finally came to experience when front-end development crossovers back-end development. After seven weeks of focusing on each topic from Ruby, to HTML/CSS, to Sinatra, to Database, to Rails, to Javascript, to jQuery, to Ajax... now I can experience the beauty of web development. I know I haven't written a technical post for a long time, so I would like to introduce a work flow I've been working on today.

Developers use Ajax to send requests to server and to make changes to the page without any page reload. With Rails, I'm able to send post requests through Ajax and retrieve records from database.

###Step 1: Use jQuery to do Ajax call
Define a click function that calls to Ajax and perform a 'put' to update the database. Notice for "task.id", I'm getting back the id from the task object.

{% highlight javascript %}
  var completeButton = $('<button class="complete">complete</button>');
  completeButton.click(function(){
    $.ajax({
      type: 'put',
      dataType: 'script',
      url: '/complete/' + task.id
    });
  });
{% endhighlight %}

###Step 2: Define a complete method in controller with Ruby on Rails
I'm finding a task record based on its id and changing its completed column (boolean) from false to true, then I call a respond_to to provoke the next javascript action.

{% highlight ruby %}
  def complete
    @task = Task.find(params[:id])
    @task.update_attribute(:completed, true)

    respond_to do |format|
      format.js
    end
  end
{% endhighlight %}

###Step 3: Continue the action with jQuery
In my views folder, I have complete.js.erb with the following code and remove the appropriate task once respond_to in controller calls. This continues to execute javascript action even after Ajax call.

{% highlight javascript %}
  var task = $("li[data-id=" + <%= @task.id %> + "]");
  task.remove();
{% endhighlight %}

My short example summarizes the way Javascript interacts with Rails and this crossover definitely will expand the possibilities for my future projects even more. I'm sure this is just a small part of what front-end and back-end can do together, but I'm excited enough. With project two coming through, I'm looking forward to have a project that is useful to New Yorkers and surrounds data analytics and visual display.
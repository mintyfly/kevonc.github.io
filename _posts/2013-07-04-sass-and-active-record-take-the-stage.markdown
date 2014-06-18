---
layout: post
title: "Sass and Active Record Take The Stage"
date: 2013-07-04 19:58
categories: webdev
tags: [wdi, coding]
---

Happy July 4th! To do web development, sometimes it's nice to get away from the computer and relax mind and body from coding for awhile. However, today I feel that I don't need a break yet and would like to boost my learning, so I dive into Sass for the afternoon. The reason I pick Sass is because Sass is built into Rails, so that it is easier to implement than LESS. If you haven't heard of Sass, it stands for Syntactically Awesome Stylesheets, which is an extension to CSS3 to make building stylesheets simple, fast, and fun.

I have played with Sass before, mostly setting variables and nesting. Today I learn more about parent selector, a bunch of color utility functions, writing conditional statements, and many more! It is truly powerful if you have experienced the pain of writing repetitive code in CSS, and not just that, the flexibility Sass provides makes the front-end design of the webpage consistent.

 In CSS, if you have two classes, say .bagel and .croissant, and they both have the same background-color and border, you usually copy and paste the exact code into both class like this.

{% highlight css %}
.bagel {
 background-color: #000;
 border: 1px solid #fff;
}

.croissant {
 background-color: #000;
 border: 1px solid #fff;
 color: red;
}
{% endhighlight %}

Now with Sass, you can either use mixin (@include) or just @extend to incorporate the styles.

Using mixin:

{% highlight scss %}
@mixin breakfast {
 background-color: #000;
 border: 1px solid #fff;
}

.bagel {
 @include breakfast;
}

.croissant {
 @include breakfast;
 color: red;
}
{% endhighlight %}

Wonderful.



Also, I would like to talk about Active Record today. Having been doing SQL for the past few days, I am not tired of it but I know there is a better way to interact with the database. Early this week Active Record was introduced, and there was no looking back to SQL. Official farewell to SQL.

I played around with Active Record for my assignment yesterday and finally came to realize the power of AR, it was so so smart. Multi-lines of code instantly becomes one line. When you are grabbing params from a form, it knows everything you're doing and you can simply pass in (params) and done! The methods provided are also useful, such as find by, select, destroy etc. Knowing how to use AR, the time to "Rails" will arrive in no time! Can't be more excited!

Once again, Happy Independence Day!
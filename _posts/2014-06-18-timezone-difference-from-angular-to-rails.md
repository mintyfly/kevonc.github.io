---
layout: post
title: "Timezone Difference from Angular to Rails"
date: 2014-06-18 16:09
categories: webdev
tags: [coding rails angular]
---

Lately I have been working on an internal project at Favorite Medium that uses Angular JS for web interface and Rails for API. I use this stack because I was desperate to learn Angular JS, and I prove my desire right by liking Angular JS a lot. I encountered one issue regarding how Angular and Rails interpret time differently based on timezone and it reverts any date I input in the form by a day. This is how I solve it.

In the app, there are multiple date fields, here let's say Date of Birth. The user inputs his DOB on a form and sends a request to the Rails API to update the record, straight forward enough. The problem I was having was a time difference issue: when a user inputs March 1st, 1990 as his DOB, Angular interprets it as 1990-03-01 00:00 along with your time zone of +08 00. The date reaches Rails and because it is using UTC, it flips the time 8 hours back so that the datetime is now 1990-02-28 16:00, and if your database column is Date, it will save as 1990-02-28, missing one day! It was quite an annoying issue because I do not care about the time zone difference, I simply want to state a correct date.

Coming to the conclusion, I decided to modify the datetime on client side to make up for the timezone difference. I wrote a Date service with a function to add the timezone offset.

{% highlight javascript %}
addTimezoneDiff: function (object) {
  var timeDiff = Math.abs(new Date().getTimezoneOffset());
    angular.forEach(object, function(value, key) {
      if (value !== null && typeof value.getMonth === 'function') {
        object[key] = new Date(value * 1 + (1000 * 60 * timeDiff));
      }
    });
  return object;
}
{% endhighlight %}

Basically what it does is instead of passing 1990-03-01 00:00, it passes 1990-03-01 08:00 to Rails and Rails will fix it by flipping it back to 1990-03-01 00:00. To be honest, I do not like this approach and I beleive there is a better way. I am happy to take any advice if any of you stumble upon my post; in the meanwhile, this works for me.

###UPDATES:
I posted the question on <a href="http://stackoverflow.com/questions/24298997/timezone-offset-in-angular-js-and-rails">StackOverflow</a> and received a better solution from <a href="http://stackoverflow.com/users/634824/matt-johnson">Matt Johnson</a>.

{% highlight javascript %}
var dt = //  whatever Date object you get from the control
dt.setHours(dt.getHours() + 12); // adjust to noon
var pad = function(n) { return (n < 10 ? '0' : '') + n; }
var dob = dt.getFullYear() + '-' + pad(dt.getMonth()+1) + '-' + pad(dt.getDate());
{% endhighlight %}

---
layout: post
title: "Write Your Own Quicksort Algorithm"
date: 2013-08-30 10:43
categories: webdev
tags: [compsci, coding]
---

Week 11, we're wrapping up the immersive program and getting ready for final project. This week was mostly Computer Science topics which included sorting algorithm which is very interesting in my point of view. There are <a href="http://en.wikipedia.org/wiki/Sorting_algorithm">a ton of sorting algorithms</a> out there and all of them work, but the key is which one performs the sorting task faster. The popular ones are <a href="http://en.wikipedia.org/wiki/Bubble_sort">Bubblesort</a>, <a href="http://en.wikipedia.org/wiki/Insertion_sort">Insertion Sort</a>, <a href="http://en.wikipedia.org/wiki/Bogosort">Bogosort</a> (the inefficient one), and of course, <a href="http://en.wikipedia.org/wiki/Quicksort">Quicksort</a>. Ruby natively uses Quicksort. Here I want to show a sort function I wrote in JavaScript.

Before that, let's talk about the concept behind Quicksort. The logic is basically pick a middle point (pivot), bring all the numbers lower than pivot to the left, and numbers larger than pivot to the right. This creates 3 arrays from 1 array. Then you run the same function to the 3 arrays again (this is called recursive function) until all the arrays each contains 1 number. It looks like this:

{% highlight javascript %}
[4,13,9,7,1,2,8] // 7 is pivot
[4,1,2] [7] [13,9,8] // Run the same function on [4,1,2] with pivot of 1 and [13,9,8] with pivot of 9
[][1][4,2] [7] [8][9][13] // Run the same function again on [4,2], this time the pivot is 2
[][1][][2][4] [7] [8][9][13] // All sorted
{% endhighlight %}

Did you see a pattern here? We're running a recursive function that runs until all arrays have a length of 1. Let's look at the code!

{% highlight javascript %}
Array.prototype.sort = function() {
  var length = this.length,
      less = [],
      equal = [],
      greater = [],
      pivot;

  if (length > 1) {
    pivot = this[parseInt(length / 2)];
    for ( var i = 0; i < length; i++ ) {
      num = this[i];
      if (num < pivot) {
        less.push(num);
      } else if (num === pivot) {
        equal.push(num);
      } else if (num > pivot) {
        greater.push(num);
      }
    }
  } else {
    return this;
  }

  return less.sort().concat(equal, greater.sort());
};
{% endhighlight %}

The code is self-explanatory, the if statement looks at the length of the array and determine whether to just return it (if there is only 1 number) or run down to split into 3 arrays (if there are 2 or more numbers). The focus should be on the last line where the less array and greater array are being sorted and all three arrays are added up and pushed up to the last layer, this way the recursive function can get back to the top layer and return the nicely sorted array!

Share with me your way of writing a Quicksort algorithm or a sorting algorithm you write in a different language. I would love to see them!
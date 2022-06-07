---
layout: post
title:  "Anonymous Functions in Python"
date:   2022-06-07 12:15:00
categories: web dev
---

One of the more powerful aspects of Python is that it allows for a style of programming called functional programming, which means that you’re allowed to pass functions around just as if they were variables or values. Sometimes we take this for granted, but not all languages allow this!

To explain anonymous functions, let's also learn about the filter and map functions.

**Filter:**

Let's say we want to make a new list using the filter function. Filter is a function that takes two things - a function and a list - and then applies that function to every item in the list in order to see if that item should be included in the resulting new list.
	

**#Using the filter function:**

{% highlight Python %}	
def is_multiple_of_three(x):
	    return x % 3 == 0
	
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
	
new_list =  filter(is_multiple_of_three, nums)
{% endhighlight %}

In the example above we are creating a new list called new_list which uses filter to combine the function is_multiple_of_three with the list we already made called nums, thus giving us a new list with just those numbers [3, 6, 9]


**#Using basic list comprehension**
	
Using the filter function is very similar to list comprehensions, for example:

{% highlight Python %}		
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

new_list = [i for i in nums if i % 3 == 0]
{% endhighlight %}

In the example list comprehension above, we are saying create a new list, then make a new number for each number in the list nums if that number in nums is divisible by 3. So we ditch the pre-made function and do it in line.
	
	
**#Using Anonymous Functions**

{% highlight Python %}	
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
new_list = filter(lambda x: x % 3 == 0, nums)
{% endhighlight %}

In the above example, we are going to create a new list using the filter function but we have a new friend, lambda, being introduced. Lambda x says "x % 3 == 0". Just like our "if" in the list comprehension and just like the is_multiple_of_three function in the first filter example. So here, we can see that we are using filter pretty similarly as to our previous example, but instead of needing to create a separate function for is_multiple_of_three, we can just write it in line. Some examples it's hard to see why we would use it over list comprehension, and in Python you often will use list comprehensions but it is an important concept in programming in general.
	

So, the filter function designates which elements of the list you want to keep. Only odd numbers, only numbers who would be even if doubled, only numbers divisible by three and so on. In the filter we specify things like this and then add those to a list.

Using the map function, we designate what we would like to DO to the items we chose.

For example, if we want to choose every odd number and then multiply the odd numbers we picked by 2. We can also use map without a filter as well and it works similarly to "for i in nums" - it just does it to every single element of the list.

Before we go on to showing mapping, first a quick filter review:

{% highlight Python %}
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

new_list = filter(lambda x: x % 3 == 0, nums)
{% endhighlight %}

  *WORKS THE SAME AS:*

{% highlight Python %}				
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

new_list = []

    for i in nums:

        If x % 3 == 0:

            new_list.append(i)

{% endhighlight %}	

Now with mapping:

{% highlight Python %}	
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

map(lambda x: x * 2, nums)
{% endhighlight %}
	
     WORKS THE SAME AS:

{% highlight Python %}	
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

new_list = []

    for i in nums:

        new_list.append(i * 2)
{% endhighlight %}

As we can see, in the filter example we are adding a number to our new list if it is divisible by 3.

In the mapping example, we are adding every item from nums into new_list but multiplying each number by 2.

We can easily combine both the map and filter function into one line when we use list comprehensions:

	nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

	new_list = [x * 2 for i in nums if x % 3 == 0]

                ^^^^^               ^^^^^^^^^^^^^
            *MAP^*                     *FILTER^*
	
	
However it is a little less clean when we use anonymous functions:

{% highlight Python %}
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

new_list = filter(lambda x: x % 3 == 0, nums)
{% endhighlight %}

Above, we write an anonymous function to specify which elements we want from nums in our new list

{% highlight Python %}
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

new_list = map(lambda x: x * 2, nums)
{% endhighlight %}

Above, we write an anonymous function to get every number from nums in our new list and multiply each number by 2
	

Lambdas are especially useful when you need a quick function to do some work for you.

If you plan on creating a function you’ll use over and over, you’re better off using def and giving that function a name.

We can also use anonymous functions with ranges:
{% highlight Python %}
squares = [x ** 2 for x in range(1, 11)]
{% endhighlight %}

^  A list comprehension where we make a list called squares. We square each number from 1-10.

{% highlight Python %}
print(filter(lambda x: x in range(30, 71), squares))
#[36, 49, 64]   <-- What it would print
{% endhighlight %}

^  We print our anonymous function which pulls out just the numbers from squares which are in the range of 30-70

We can use anonymous functions with strings as well, for exmaple if we only wanted to get "Python" out of our languages list:

Example One:

{% highlight Python %}
languages = ["HTML", "JavaScript", "Python", "Ruby"]
		
print(filter(lambda x: x == "Python", languages))
#--- Prints ['Python']---
{% endhighlight %}
	


Example Two:

{% highlight Python %}
garbled = "IXXX aXXmX aXXXnXoXXXXXtXhXeXXXXrX sXXXXeXcXXXrXeXt mXXeXsXXXsXaXXXXXXgXeX!XX"
		
message = filter(lambda x: x != "X", garbled)

print(message)
#------Prints I am another secret message!  ---
{% endhighlight %}
	
	
**Summary:**

So, when programming you will need to make a choice about whether it is best to use for loops and fully written functions, list comprehension, or anonymous functions. There usually isn't a "right" answer and it will depend on context.
	
For example, If you want to just use map or filter alone, an anonymous function is probably the cleaner way to go.
	
If you want to use both, then a list comprehension is probably the cleaner way to go.
	
If your function is more involved, going to be used again, maybe is pushing to a database, etc. then you will oftentimes want to write it the classic way of having a formally defined function and for loops, etc.
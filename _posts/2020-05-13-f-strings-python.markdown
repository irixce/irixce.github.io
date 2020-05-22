---
layout: post
title:  "f-strings in Python"
date:   2020-05-13
categories: python strings
---

Formatting strings is one of the most common operations in programming.
If you program in Python, you are probably aware of the  `%s`, `str.format()`,  or the `string.Template` methods for string formatting.
While each method has its own advantages, there are also some limitations.

Python 3.6 introduces a simpler, concise, and more readable way of formatting string literals with **f-strings**, or "formatted strings".

Within f-strings, `{}` are used as 

{% highlight python %}
>>> val = 25
>>>f'{val}'
'25'
{% endhighlight %}

F-strings can also be used to perform evaluations on any valid Python expressions, including function and method calls:

For example, we can evaluate the value of dictionary `d` using its key `name`:
{% highlight python %}
>>> d = {"name": "Ira"}
>>> f'{d["name"]}'
"Ira"
{% endhighlight %}
>

Or we can use it to print multiples of 20:

{% highlight python %}
>>> for x in range(3):
      print(f'Example {x} : {20*x}')
...
Example 0 : 0
Example 1 : 20
Example 2 : 40
{% endhighlight %}

We can also define a recursive function, `fib(n)`, that returns the n-th Fibonacci number and use f-strings
to format the result. 
{%highlight python%}
>>> def fib(i):
        if i == 0:
            return 0
        if i == 1:
            return 1
        return fib(i-1) + fib(i-2) 
{% endhighlight %}

We first define a variable `n` to denote the n-th Fibonacci number we'd like to return.
Within the f-string, a placeholder is used to hold the variable value and a call to the function is made within the `{}` of the f-string. 
{% highlight python %}
>>> n = 4
>>> f'The {n}th Fibonacci number is {fib(n)}'
'The 4th Fibonacci number is 3'
{% endhighlight %}

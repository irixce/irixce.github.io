---
layout: post
title:  "f-strings in Python"
date:   2020-05-13
categories: python numpy
---

If you program in Python, you are probably aware of the  `%s`, `str.format()`,  or the `string.Template` methods.

f-strings, or "formatted strings" were introduced in Python 3.6, and offer a simpler, concise, more readable
way of formatting string literals.

{% highlight python %}
>>> d = {"name": "Ira"}
>>> f'{d["name"]}'
"Ira"
{% endhighlight %}
>



{% highlight python %}
>>> for x in range(3):
...   print(f'Example {x} : {20*x}')
... 
Example 0 : 0
Example 1 : 20
Example 2 : 40
{% endhighlight %}
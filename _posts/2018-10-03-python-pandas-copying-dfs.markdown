---
layout: post
title:  "Python Pandas: Tips & Tricks"
date:   2018-10-03
categories: python pandas data-frames
---

## Copying a Column of a DataFrame

### Problem Statement 1: Updating An Existing DataFrame
 
Given a sample pandas DataFrame `df` with two columns containing user `name` and `age`, 
we want to update `df` with a copy of the `age` column.


{% highlight python %}
# A pre-existing data-frame df with a name and age column, 3 entries each 
>>> df
    name    age
0   Alex      3
1   Annie     4
2   Jess      5
{% endhighlight %}

Executing `df['age_copy'] = df['age']` will update the DataFrame `df` with a newly-added column labeled `age_copy`.

{% highlight python %}
# df updated with a new column, age_copy
>>> df['age_copy'] = df['age']
>>> df
    name    age   age_copy
0   Alex      3          3
1   Annie     4          4
2   Jess      5          5
{% endhighlight %}

### Problem Statement 2: Creating a New DataFrame

Given a sample pandas DataFrame `df` with two columns containing user `name` and `age`, 
we want to create a new DataFrame, `df_new`, with a copy of `df`’s `age` column.

{% highlight python %}
# A pre-existing data-frame df with a name and age column, 3 entries each 
>>> df
    name    age
0   Alex      3
1   Annie     4
2   Jess      5
{% endhighlight %}

Executing `df_new = pd.DataFrame({'age_copy': df['age']})` creates a new DataFrame `df_new` with a column 
labeled `age_copy`,which is populated with content copied from `df['age']`.

{% highlight python %}
# A new data-frame df_new
# its age_copy column is copied from df
>>> df_new = pd.DataFrame({'age_copy': df['age']})
>>> df_new
    age_copy
0          3
1          4
2          5
{% endhighlight %}
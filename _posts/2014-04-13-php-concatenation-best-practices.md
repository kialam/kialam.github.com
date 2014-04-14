---
layout: post
title: "PHP Concatenation Best Practices"
description: ""
category: programming
tags: [coding, programming, PHP, strings]
excerpt: In my opinion, concatenation of strings in any language has never looked pretty.
googlewebfonts: Lekton
---
{% include JB/setup %}

In my opinion, concatenation of strings in any language has never looked pretty.

Javascript:
{% highlight javascript %}
var hello = "hi there";
var name = "Kia Lam";
var greeting = hello + '' + name;
{% endhighlight %}
Python:
{% highlight python %}
>>> name = 'Kia Lam'
>>> print 'hi there %s' % name
{% endhighlight %}
PHP:
{% highlight php startinline %}
$hello = "hi there";
$name = "Kia Lam";
$greeting = $hello . '' . $name
{% endhighlight %}

While browsing the PHP manual I found an entry by a user 'K.Alex' that intrigued me.
{% highlight php startinline %}
// This works:
 echo "qwe{$a}rty"; // qwe12345rty, using braces
 echo "qwe" . $a . "rty"; // qwe12345rty, concatenation used

// Does not work:
 echo 'qwe{$a}rty'; // qwe{$a}rty, single quotes are not parsed
 echo "qwe$arty"; // qwe, because $a became $arty, which is undefined
 {% endhighlight %}

I find the above method to be really elegant and a lot more human-readable than the method I've been using. So to put it all together, here's string concatentation using PHP - the elegant way:
{% highlight php startinline %}
"{$hello} {$name}";
{% endhighlight %}

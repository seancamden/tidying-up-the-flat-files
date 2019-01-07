---
id: 542
title: Playing with TextBlob
date: 2014-01-22T22:57:55+00:00
author: seancamden
layout: post
guid: http://www.seancamden.com/?p=542
permalink: /?p=542
st_cached:
  - '<ul class="socialize-this"><li><a href="http://del.icio.us/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D542&title=Playing+with+TextBlob" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/del.png" width="48px" height="48px" alt="Delicious" title="Delicious" /></a></li><li><a href="http://www.facebook.com/sharer.php?u=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D542&t=Playing+with+TextBlob" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/facebook.png" width="48px" height="48px" alt="Facebook" title="Facebook" /></a></li><li><a href="http://digg.com/submit?phase=2&url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D542" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/digg.png" width="48px" height="48px" alt="Digg" title="Digg" /></a></li><li><a href="http://www.reddit.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D542&title=Playing+with+TextBlob" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/reddit.png" width="48px" height="48px" alt="Reddit" title="Reddit" /></a></li><li><a href="http://www.stumbleupon.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D542&title=Playing+with+TextBlob" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/stumble.png" width="48px" height="48px" alt="StumbleUpon" title="StumbleUpon" /></a></li><li><a href="http://twitter.com/home?status=Currently Reading http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D542"  target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/twitter.png" width="48px" height="48px" alt="Twitter" title="Twitter" /></a></li></ul>'
st_cached_time:
  - "1390441023"
st_tiny_url:
  - http://is.gd/PhL0UJ
st_twitter:
  - "0"
st_reddit:
  - "0"
st_social_score:
  - "0"
st_last_socialized:
  - "0"
---
TextBlob is a fun Python library that allows one to parse blocks of text in neat ways.

To use it, all you need is a computer with [Python](http://www.python.org/) on it. I&#8217;m using [Linux Mint](http://linuxmint.com/) with Python 2.7.3. Installation of TextBlob is covered pretty well on [Steve Loria&#8217;s TextBlob page](http://textblob.readthedocs.org/en/latest/).

To begin I open my Python interpreter and import TextBlob.
  
`>>> from textblob import TextBlob`

Then I load my text. I&#8217;m using a chunk of [The Brothers Karamazov](http://www.gutenberg.org/ebooks/28054).
  
`>>> with open(r"/home/sean/Documents/text-blobs/the-brothers-karamazov/brothers-044") as infile:<br />
... &nbsp;&nbsp;data = infile.read()<br />
... &nbsp;&nbsp;myblob = TextBlob(data)<br />
...<br />
` 

Now I have a TextBlob object named &#8220;myblob&#8221; and I can do fun stuff with it. For instance, I can loop through it and pull out all the adjectives.
  
`>>> for value,key in sorted(set(myblob.tags)):<br />
... &nbsp;&nbsp;if key == "JJ":<br />
... &nbsp;&nbsp;&nbsp;&nbsp;print key,value<br />
...<br />
JJ back<br />
JJ back-way<br />
JJ black<br />
JJ certain<br />
JJ civil<br />
JJ clear<br />
--and so on...<br />
` 

By setting up my `for` loop with the `sorted()` and `set()` methods, the output is alphabetized and will contain no duplicates.

But suppose I only want to see the adjectives that are five characters long. Then I use Python&#8217;s `len()` method. Like so:
  
`>>> for value,key in sorted(set(myblob.tags)):<br />
... &nbsp;&nbsp;if key == "JJ" and len(value) == 5:<br />
... &nbsp;&nbsp;&nbsp;&nbsp;print key,value<br />
...<br />
JJ black<br />
JJ civil<br />
JJ clear<br />
JJ equal<br />
JJ first<br />
--and so on...<br />
` 

I can sort for verbs, too; in fact, any part of speech listed in the [Penn Treebank II tag set](http://www.clips.ua.ac.be/pages/mbsp-tags) will work.

The Penn Treebank code for gerunds is VBG. But sometimes I want all the words that end in &#8220;ing&#8221; even if it&#8217;s not a gerund. In that case, I use Python&#8217;s string methods instead. Like so:
  
`>>> for value,key in sorted(set(myblob.tags)):<br />
... &nbsp;&nbsp;if value[-3:] == "ing":<br />
... &nbsp;&nbsp;&nbsp;&nbsp;print key,value<br />
...<br />
VBG according<br />
NN anything<br />
VBG behaving<br />
VBG bringing<br />
--and so on...<br />
` 

Using Python&#8217;s handy string methods I can easily test for a word that begins with a particular letter, too. Here I&#8217;ll throw in the `lower()` method to match regardless of case:
  
`>>> for value,key in sorted(set(myblob.tags)):<br />
... &nbsp;&nbsp;if value[0].lower() == "a":<br />
... &nbsp;&nbsp;&nbsp;&nbsp;print key,value<br />
...<br />
DT A<br />
IN Among<br />
NNP April<br />
IN At<br />
DT a<br />
IN about<br />
VBG according<br />
VBN accustomed<br />
--and so on...<br />
` 

But what if I want to match all the words that start with vowels? Well, I think I&#8217;m going to need a [regular expression](http://www.regular-expressions.info/) to do that. (I love regular expressions.)

First I&#8217;ll import Python&#8217;s regex library and then create my regular expression.
  
`>>> import re<br />
>>> reg = re.compile('^[aeiou]\w*', re.IGNORECASE)<br />
` 

As you can see, I&#8217;m looking for any word that begins &#8220;`^`&#8221; with a vowel &#8220;`[aeiou]`&#8221; and is followed by zero or more &#8220;`*`&#8221; alphanumeric characters &#8220;`\w`&#8221; and I want to ignore case. Then I just use another `for` loop, only this time with my new regex. Like so:
  
`>>> for value,key in sorted(set(myblob.tags)):<br />
... &nbsp;&nbsp;if reg.match(value):<br />
... &nbsp;&nbsp;&nbsp;&nbsp;print key,value<br />
...<br />
DT A<br />
IN Among<br />
NNP April<br />
IN At<br />
DT Every<br />
IN If<br />
IN In<br />
PRP It<br />
IN Of<br />
DT a<br />
IN about<br />
--and so on...<br />
` 

All the base form verbs that start with a vowel:
  
`>>> for value,key in sorted(set(myblob.tags)):<br />
... &nbsp;&nbsp;if key == "VB" and reg.match(value):<br />
... &nbsp;&nbsp;&nbsp;&nbsp;print key,value<br />
...<br />
VB act<br />
VB entertain<br />
VB estrange<br />
VB in<br />
VB into<br />
` 

Pretty cool, right?
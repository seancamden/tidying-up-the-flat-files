---
id: 540
title: Getting Started with TextBlob
date: 2013-12-12T23:03:26+00:00
author: seancamden
layout: revision
guid: http://www.seancamden.com/2013/12/12/538-revision-v1/
permalink: /?p=540
---
I&#8217;ve been making daily posts to http://twitter/wagonlips for a few years now. It started out simply as quotes from whatever book I was reading at the time, starting with Moby Dick. It evolved and now it&#8217;s a sort of literary mashup that combines the Public Domain works of authors into something new. Currently, W. B. Yeats provides the structure and Dostoyevsky provides the words and everything is written backwards, like a reverse Mad-Libs. About a year ago I started drawing pictures in the spaces between the words, just for fun.

I had been using the excellent regex tool at http://gskinner.com/RegExr/ to sort out the words I needed to fit the required patterns. This method was good, and I enjoy regular expressions. But it was difficult, too. Regular expressions don&#8217;t really help you find words by type, only by spelling and length. Matching for words that end in &#8216;ing&#8217; will work if you want gerunds, but plural nouns or adjectives or verbs of a specific tense are pretty much impossible.

TextBlob can totally do all that. It&#8217;s a Python library that will take a block of text and tag all the words for you. Then it&#8217;s a simple matter to loop over the dictionary and filter by type, by length, by letters, anything. It&#8217;s really great.
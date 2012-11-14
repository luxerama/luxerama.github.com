---
layout: post
title: "getting a document's distance using mongoid and moped"
date: 2012-11-14 12:02
comments: true
categories: [MongoDB, Mongoid, Geospacial]
---

## What am I trying to do?
I am currently working on a project that requires the retrieval of geospacial documents from a collection. Each time I retrive documents I also need to include the distance in the resultset. Furthermore I need to be able to paginate through the documents.

## Problems
There were two issues I had to address. The first one was related to Mongoid directly, however the second one is a little more tricky as I need to use MongoDB functionality that has yet to be implemented thus I needed to implement a workaround rather than a straight fix.
### Mongoid does not return the distance when using `Model.near`
So far I have been unable to find a way to return the distnace with Mongoid's near wrapper. Because of this limitation I am forced to query directly through [Moped](http://mongoid.org/en/moped/).
After reading around, the easiest way to send queries directly through Moped was outlined in this Gist:
{% gist 488000 %} 
which accompanied this [Github issue](https://github.com/mongoid/mongoid/issues/139)

From that we can work out that the following will work in Mongoid:
{% gist 4071837 %}

### MongoDB is missing a .skip() equivalent for $geoNear
In this section I will shortly discuss the workarounds I had to deploy in order to get pagination working.
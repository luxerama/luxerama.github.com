---
layout: post
title: "Homebrew: memcache without the D"
date: 2012-08-16 21:06
comments: true
categories: [Homebrew, PHP5]
---
## What is it?
Memcache is a memcached client from [PECL](http://pecl.php.net/package/memcache)
## Why am I even doing this?
Unfortuantely at my current job we are still running some legacy systems that are still relying on fairly old school packages for their day-to-day runnings.
Because I am sick of having to dig up the manual on how to compile memcache everytime I build a development machine I thought I make mylife a little easier and automate the compile via brew.
## Where is it?
I am hosting my own brew [repository](https://github.com/luxerama/homebrew-weizen) and you can tap it (if you are running at least brew v0.9) with `brew tap luxerama/weizen`, then just install it with `brew install memcache`.
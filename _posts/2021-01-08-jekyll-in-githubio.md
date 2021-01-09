---
title: Jekyll in github.io
tags:
- jekyll
date: '2021-01-08 19:00:00'
permalink: "/posts/2021/01/08/blog"
---

## Jekyll 

Jekyll is a simple, blog-aware, static site generator for personal, project, or organization sites. 

Github.io support Jekyll for personal site 

--------
## Some notes on Jekyll
 Collection: *A set of posts*
 navigation.yml:  *define elements in the page, such as header*

---

## Display pdf in the page
It seems Safari does not handle object and embed tag well to display a pdf file (No problem in Chrome). 
The img tag works well in Safari, but multiple-page pdf will have to be splitted into single pages.
Current solution is to use iframe tag

---

## A local Jekyll manager
I installed a local Jekyll plugin [jekyll-manager](https://github.com/ashmaroli/jekyll-manager).

```
bundle exec jekyll serve
http://localhost:4000/admin
```
### Note:
Installation of Jekyll-manager in macOS:

Add the following to your site's Gemfile
```
gem 'jekyll-manager', group: :jekyll_plugins
```
Run 
```
bundle install
```
However, Xcode changed path of dependencies. If errors were popped up, clear ruby installation and reinstall

---
layout: post
title: US International Flags Map
modified:
categories:
excerpt:
tags: [programming, d3, javascript, vexillology]
image:
  feature:
date: 2016-07-16T20:12:41-06:00
comments: true
---

I quite enjoy learning about flags and try to pick one up as a souvenir whenever I visit a new country.  A couple years ago, I stumbled upon an [online community](http://www.reddit.com/r/vexillology) of other flag lovers, and stop in from time to time to see what's new.

Recently, I stumbled upon [a post](https://www.reddit.com/r/vexillology/comments/4t2b50/my_roughly_somewhat_us_state_to_country/) that had a really cool concept.  What if you filled in each US state with a flag of another country with roughly the same population.  The result puts a lot of things in perspective, for instance, just how populous some US states are, as well as how small many countries are compared to the United States.

I was a big fan of the post, and decided to recreate it using [D3.js](https://d3js.org/).  D3 is a JavaScript library for creating dynamic visualizations based off data.  In this case, I am using GeoJSON data for the United States, and a list of states, country flags, and some extra population information.

<div id="map-canvas"></div>
<div id="tooltip-container"></div>

I'm no D3 master (yet), but once I got the map set up and the images downloaded, most of the state flags fell in to place without much fuss.  I really like this concept and would like to explore it with other concepts (GDP comes to mind, though I don't want to stroke [California](http://www.latimes.com/business/la-fi-california-world-economy-20150702-story.html)'s ego *too* much...)

I've put the [source code](https://github.com/arbrown/flagmap) on Github, and I'm open to any improvements or corrections.  Let me know in the Github issues or the comments below, or drop me an email.

<script src="//d3js.org/d3.v3.min.js" charset="utf-8"></script>
<script src="//d3js.org/topojson.v1.min.js"></script>
<script src="https://code.jquery.com/jquery-2.1.4.min.js"></script>
<script src="/assets/js/flagmap/script.js"></script>

<link rel="stylesheet" href="/assets/css/flagmap/flagmap.css">

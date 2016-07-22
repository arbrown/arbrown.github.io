---
layout: post
title: US International Flags Map by Area
modified:
categories:
excerpt:
tags: [programming, d3, javascript, vexillology]
image:
  feature:
date: 2016-07-21T20:46:39-06:00
comments: true
---

Last week, I [posted a map]({% post_url 2016-07-16-us-international-flags-map %}) of the United States with international flag backgrounds for each state corresponding to a similarly populated country.

This week, I've gone ahead and created a new map, this time with the backgrounds corresponding to the closest sized country in the world. I didn't prevent duplicates, so if two states are close in size (see South Dakota and Nebraska), they will likely have the same country flag, which produces some interesting results.

<div id="map-canvas"></div>
<div id="tooltip-container"></div>

I mostly re-used the same code, with one important change.  I [updated the code](https://github.com/arbrown/flagmap/blob/2084ced7c72958c4ba0a6a1d4e504d395c4e02fb/scriptv2.js#L59-L86) that scales flag images to be an appropriate size for each state.  The new solution is much more general, and I think produces better looking images.

As usual, feel free to poke around the code, examine the map, and point out how I can improve it.

<script src="//d3js.org/d3.v3.min.js" charset="utf-8"></script>
<script src="//d3js.org/topojson.v1.min.js"></script>
<script src="https://code.jquery.com/jquery-2.1.4.min.js"></script>
<script src="/assets/js/flagmap/scriptv2.js"></script>

<link rel="stylesheet" href="/assets/css/flagmap/flagmap.css">

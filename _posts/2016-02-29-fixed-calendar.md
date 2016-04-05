---
layout: post
title: Fixed Calendar
modified:
categories:
excerpt: Happy Leap Day!  I have a cousin who was born on February 29th.  I guess today must be her 9th birthday, which might come as a surprise to her kids...
tags: [business, programming, javascript]
image:
  feature:
date: 2016-02-29T15:51:22-07:00
comments: true
---
<script src="https://code.jquery.com/jquery-2.1.4.min.js"></script>
<script src="/assets/js/calendar/fixedCalendar.js"></script>
<script src="/assets/js/calendar/blogPost.js"></script>
<link rel="stylesheet" href="/assets/css/calendar/calendar.css">

Happy Leap Day!  I have a cousin who was born on February 29th.  I guess today must be her 9th birthday, which might come as a surprise to her kids...  What kind of calendar has a day that just shows up every four years (except [when it doesn't](https://github.com/arbrown/fixed-calendar/blob/9d651fd482f603de60db6029c4438e14d50154bb/fixedCalendar.js#L10)) like some sort of deadbeat dad?  Surely there must be a better way!

### Our Calendar (kind of) Sucks
The [Gregorian calendar](https://en.wikipedia.org/wiki/Gregorian_calendar) was introduced to the world in 1582.  It was an incremental improvement to the [Julian calendar](https://en.wikipedia.org/wiki/Julian_calendar), which it replaced.  The new calendar moved Easter around a bit and made calculation of leap years even more complicated.  The Gregorian calendar was certainly cutting edge 16th-century technology when it was introduced, but then again, so was [the pencil](https://en.wikipedia.org/wiki/Pencil#Wood_holders_added) and [the letter J](https://en.wikipedia.org/wiki/J).
<figure>
<img src="/images/calvin.png">
<figcaption>The Gregorian calendar and Calvinism were all the rage in the 16th century.</figcaption>
</figure>

Luckily, there *is* a better way. Hopefully you're not the superstitious type.  Could you handle a year with 13 months instead of 12?  What if _every_ month had a Friday the 13th?  Sound crazy?  It might just be the best idea you read today.

## Today is
{: style="text-align: center"}

<time class="icon"><em>Monday </em><strong>February </strong><span>29</span>
</time>

## Really...
{: style="text-align: center"}

### The Idea
The [International Fixed Calendar](https://en.wikipedia.org/wiki/International_Fixed_Calendar) was created to fix the mess that is our current calendar system.  It has 13 months of exactly 28 days (with an annual _year day_ holiday and a _leap day_ in the same years as now that exist separate from any month.)  Every month starts on a Sunday and ends on a Saturday and has exactly 4 weeks.  [Much](http://www.citylab.com/work/2014/12/the-world-almost-had-a-13-month-calendar/383610/) and [more](http://gizmodo.com/5917654/kodak-used-a-calendar-with-13-months) has already been written on the history of this calendar system.  There's even [a great podcast episode](http://99percentinvisible.org/episode/the-calendar/) on the history of calendars that touches on the fixed calendar.

Quick!  Off the top of your head, which day of the week will February 12th, 2018 be?  How many days are there between July 4th and October 31st of this year?  Working with dates is annoying and [programming with them](http://www.dadhacker.com/blog/?p=1585) is even worse.  There's nothing we can do about the hot mess of calendar systems that existed in the past, but shouldn't we do something to make the problem more manageable for the future?

<figure>
<img src="https://upload.wikimedia.org/wikipedia/commons/d/d8/50yearcalendar.JPG">
<figcaption>You shouldn't need hardware to tell you what day of the week it is, though I admit that is a classy looking hunk of metal.</figcaption>
</figure>

The International Fixed Calendar makes it easier to deal with days of the week, and makes each month more predictable.  For instance, it's a lot easier to compare business revenue when **every** month **always** has 20 work days and 8 weekend days.  And why am I paying the same rent and cable bill for February as I do for March?  It's never the same amount of time!  These kind of things bug me; the world is crazy enough as it is, I'll take a bit more logic and structure wherever I can get it!  Needless to say, I'm a big fan of the International Fixed Calendar.

<figure>
<img src="/images/fixedcal.png">
<figcaption>This could be the last <a href="/">calendar</a> you ever buy, if it weren't for <a href="http://www.calendars.com/"><span style="font-weight: bold;">Big Calendar</span>'s</a> extensive lobbying efforts!</figcaption>
</figure>

### The Code
I'm such a fan, in fact, that I busted out my rusty JavaScript skills to write some code to convert [Gregorian](https://en.wikipedia.org/wiki/Gregorian_calendar) dates to Fixed dates.  The calendar graphic at the top of the post should display _today's_ fixed calendar date.  So, if you ever find yourself wondering what day/date today **should** be, feel free to come back to this page and check it out!  I threw the code up [on Github](https://github.com/arbrown/fixed-calendar) if you want to check it out or suggest improvements.

<figure>
{% highlight javascript%}
$(document).ready(function(){
  var fd = new Date().toFixedDate();
  var title = $('title');
  title.html(new Date().toFixedDateString() + ' - Drew Brown');
  var calendar = $('time.icon');
  calendar.html('');
  calendar.append('<em>'+fd.day+'</em>');
  calendar.append('<strong>'+fd.monthName+'</strong>');
  calendar.append('<span>'+fd.date+'</span>');
})
{%endhighlight%}
<figcaption>This code uses jQuery to replace the date in the calendar at the top of the page with a "fixed" date.</figcaption>
</figure>

So how would you handle the fixed calendar?  Would you rejoice in the predictability and consistency it provides?  Or would you be depressed to have your birthday be on a Tuesday for the rest of your life?

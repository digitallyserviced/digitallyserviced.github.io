---
layout: page
title: xcezzz's projects
image:
  feature: blessed-ceph-dash.png
comments: true
---

##My Projects
---------


##ceph monitoring dashboard

###[Blessed Ceph Dashboard](https://github.com/xcezzz/blessed-ceph-dash)

Using the blessed-contrib library for building console dashboards in node.js, I built a dashboard to monitor our Ceph cluster using the console. 

![screenshot](/images/blessed-ceph-dash.png)

_Get it today!_

{% highlight bash %}
npm install -g blessed-ceph-dash
{% endhighlight %}

####[Read More](/ceph-dash)####

---------

##blessed-contrib widgets

###[blessed-contrib](https://github.com/xcezzz/blessed-contrib)

To make the Ceph dashboard possible I had to add additional widgets to the mix. This included a **stacked guage** which provides a sort of combined progress bar. It also includes a **LCD display** widget for displaying basic text and numbers for showing stats in the dashboard.
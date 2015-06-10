---
layout: page
title: xcezzz's projects
image:
  feature: blessed-ceph-dash.png
comments: true
---

##My Projects

##ceph monitoring dashboard

###[Blessed Ceph Dashboard]((https://github.com/xcezzz/blessed-ceph-dash))

Using the blessed-contrib library for building console dashboards in node.js, I created a dashboard to monitor our Ceph cluster. 

![screenshot](/images/blessed-ceph-dash.png)


##blessed-contrib widgets

###[blessed-contrib](https://github.com/xcezzz/blessed-contrib)

To make the Ceph dashboard possible I had to add additional widgets to the mix. This included a **stacked guage** which provides a sort of combined progress bar. It also includes a **LCD display** widget for displaying basic text and numbers for showing stats in the dashboard.
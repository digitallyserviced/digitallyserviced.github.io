---
layout: post
title: Ceph Dashboard
date: 2015-06-10T14:29:46-04:00
image:
  feature: blessed-ceph-dash.png
---

###Fancy Console Dashboard

So the bosses enjoy seeing fancy graphs and real-time statistics on everything. What better way than to build a customized dashboard to show the things we want.

Recently I became interested in [blessed-contrib](https://github.com/yaronn/blessed-contrib) for building console based dashboards using node.js

Whipping up a quick dashboard to be able to monitor our microservices as well as our Ceph storage cluster was fun.

I did however need to build some extra widgets into blessed-contrib for better display of certain portions of the statistics. My changes can be seen at my own fork of [blessed-contrib](https://github.com/xcezzz/blessed-contrib). 

![blessed-ceph-dash](../images/blessed-ceph-dash.png)

*The source for the Ceph dashboard is available on GitHub*

[Get it!](https://github.com/xcezzz/blessed-ceph-dash)

###Setup Overview
The dashboard uses an express route so that you can post the output of `ceph status -f json` to it.

Since my Ceph cluster is on a private network and inaccessible from dev machines. The Ceph cluster POSTs data outbound to port 3004 (default port used in this).

###On some host
{% highlight bash %}
git clone https://github.com/xcezzz/blessed-ceph-dash.git
node index
{% endhighlight %}



###On a machine that can access the Ceph cluster
{% highlight bash %}
while true; do 
	ceph status -f json | curl -X POST \
	  -H "Content-type: application/json" \
	  -d @- http://remotehost:3004/; 
	sleep 2; 
done
{% endhighlight %}
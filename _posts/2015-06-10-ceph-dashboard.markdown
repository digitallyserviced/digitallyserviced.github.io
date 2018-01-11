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

I did however need to build some extra widgets into blessed-contrib for better display of certain portions of the statistics. My changes can be seen at my own fork of [blessed-contrib](https://github.com/digitallyserviced/blessed-contrib). 

![blessed-ceph-dash](../images/blessed-ceph-dash.png)

*The source for the Ceph dashboard is available on GitHub*

[Get it!](https://www.npmjs.com/package/blessed-ceph-dash)

###Installation

{% highlight bash %}
npm install -g blessed-ceph-dash
{% endhighlight %}

####Local Usage (ceph admin)

{% highlight bash %}
ceph-dash
{% endhighlight %}

####SSH Usage (ssh to ceph admin)

{% highlight bash %}
ceph-dash --remote=remotehost --port 22 --key /path/to/identity
{% endhighlight %}

Optionally instead of `--key` you can use `--password` and specify it on the command line.

####Dumb Dashboard

{% highlight bash %}
ceph-dash --noauto --bind 1234
{% endhighlight %}

Will start the dashboard listening on port 1234. This will output a command you would run on some server that has access to the `ceph` command with admin privileges. It would POST the JSON data to the port so that you can bypass any possible firewalling/internal networking problems that would arise from the other methods.

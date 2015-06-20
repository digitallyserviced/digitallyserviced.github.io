---
title: Version 0.1.2 of ceph-dash
date: 2015-06-20T19:03:20-04:00
layout: post
image:
    feature: blessed-ceph-dash.png
---

#New Version 0.1.2

![](../images/blessed-ceph-dash.png)

After a bit of hacking away, I have put up version 0.1.2.

This includes new features for monitoring your Ceph cluster in many different ways.

##Monitoring Methods
* Run the dashboard on a machine that is a Ceph admin.
* Monitor over an SSH connection
* Run the dashboard without automatically gathering data. Allowing for you to work up some way of gathering data manually (like pushing data to it from inside a private network)

Easy install and usage!

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




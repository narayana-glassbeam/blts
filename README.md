你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
Better Living Through Statistics: Monitoring Doesn't Have To Suck.
==================================================================


This is the source code for the demo that I used when I presented this talk to

    * PuppetConf 2012
    * again at OSDC 2013
    * at PuppetCamp Sydney 2013
    * Sysadmin Miniconf at linux.conf.au 2014
    * using Prometheus as a demo at Monitorama 2015
    * again at linux.conf.au 2016

The URL for the video from PuppetConf 2012 is http://youtu.be/eq4CnIzw-pE 

The original slide deck is at https://docs.google.com/presentation/d/1uTLggLR5HICnSyhTJyQWNeYWZ6niHyCsup7wNFByex4/pub

I presented an abridged version to the Sysadmin Miniconf at Linux.conf.au 2014, the revised slide deck is here:

https://docs.google.com/presentation/d/1Dq4eRUlkONnVnnXg6M_ZSi6xBLEwe7kjwjx74vFL1N4/pub

Monitorama 2015 slides: https://docs.google.com/presentation/d/1X1rKozAUuF2MVc1YXElFWq9wkcWv3Axdldl8LOH9Vik/edit

linux.conf.au 2016 slides: https://docs.google.com/presentation/d/1NziwSTwuz91fqsFhXeOGwyhFUoT6ght1irA_0ABLPU0/edit

To use the demo code
--------------------

The demo is of a mock service, a web application frontend, composed of a
cluster of application servers and a single loadbalancer.  The loadbalancer is
not very good, and the application servers fail often.  An antagonistic load
generator drives them past their capable limits.

[Prometheus](http://prometheus.io) is the metrics collector and alerting engine
used in this example.

The demo code uses Go but not in a Go friendly project layout.  But you
wouldn't try to import this into your code, would you?

`make` will build the things you need.

`./servers.sh` runs the servers.

`./load.sh` requires `ab` (ApacheBench) from the Apache webserver tools.

`./prom.sh` launches Prometheus with the included configuration.  You will need to change the path of the binary in this script.

`./am.sh` runs the Prometheus Alertmanager with the included configuration.  You will need to chagne the path of the binary in the script.

The subdirectory `prom` contains the main config and rules for the Prometheus tools.

This code is available under the Apache v2 license.

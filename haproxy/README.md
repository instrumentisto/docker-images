HAProxy Docker image 
====================

<img align="right" src="https://cbonte.github.io/haproxy-dconv/img/logo-med.png">
[![docker](https://img.shields.io/badge/image-quay.io%2Finstrumentisto%2Fhaproxy-green.svg)](https://quay.io/repository/instrumentisto/haproxy)
[![based](https://img.shields.io/badge/based%20on-haproxy%3A1.6.9--alpine-blue.svg)](https://hub.docker.com/_/haproxy)
[![uses](https://img.shields.io/badge/uses-s6--overlay-blue.svg)](https://github.com/just-containers/s6-overlay)
[![license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/instrumentisto/docker-images/blob/master/haproxy/LICENSE.md)
[![github](https://img.shields.io/badge/GitHub-repo-blue.svg)](https://github.com/instrumentisto/docker-images/tree/master/haproxy)

Docker image of [HAProxy TCP/HTTP load balancer](http://www.haproxy.org).



## Purpose

The problem with [official HAProxy Docker image](https://hub.docker.com/_/haproxy)
is that it produces [no logs in Docker way by default](https://github.com/dockerfile/haproxy/issues/3).
HAProxy can [only log to syslog](https://www.mail-archive.com/haproxy@formilux.org/msg17436.html)
and `syslogd` of official image is turned off by default.
It can be turned on in some [tricky way](https://github.com/dockerfile/haproxy/issues/3#issuecomment-238725290),
but if we have more than one processes in container they should be supervised
(cause what happens if some of them silently exit?).

To solve this problem this image uses [s6-overlay](https://github.com/just-containers/s6-overlay)
with `s6` supervisor.



## Configuration

Image is provided with the 
[following default configuration](https://github.com/instrumentisto/docker-images/blob/master/haproxy/rootfs/etc/haproxy/haproxy.cfg).

To override default configuration or append it you can either specify your
own `/etc/haproxy/haproxy.cfg` file or specify drop-in configuration files
in `/etc/haproxy/conf.d/` directory.



## Logs

The `syslog` of this image is configured to write everything to `/dev/stdout`.  
To change this behaviour just provide your own `/etc/syslog.conf` file
with desired log rules.

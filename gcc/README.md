GCC Docker image
================

<img align="right" src="https://gcc.gnu.org/img/gccegg-65.png">
[![image](https://img.shields.io/badge/image-quay.io%2Finstrumentisto%2Fgcc-green.svg)](https://quay.io/repository/instrumentisto/gcc)
[![based](https://img.shields.io/badge/based%20on-alpine-blue.svg)](https://hub.docker.com/_/alpine)
[![license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/instrumentisto/docker-images/blob/master/gcc/LICENSE.md)
[![github](https://img.shields.io/badge/GitHub-repo-blue.svg)](https://github.com/instrumentisto/docker-images/tree/master/gcc)

- `5.3.0`, `5.3`, `5` ([5.3.0/Dockerfile](https://github.com/instrumentisto/docker-images/blob/master/gcc/5.3.0/Dockerfile))
- `6.2.1`, `6.2`, `6`, `latest` ([6.2.1/Dockerfile](https://github.com/instrumentisto/docker-images/blob/master/gcc/6.2.1/Dockerfile))

Docker image for compiling C/C++ applications on Alpine Linux.



## Purpose

Alpine Linux has [different `libc`](https://www.musl-libc.org) (not GNU)
than other common distros.  
So, if we compile some application with
[official GCC Docker image](https://hub.docker.com/_/gcc) (Debian based),
with a high probability it won't run on Alpine Linux.

*For Alpine Linux we have to compile things in Alpine Linux.*

That is the purpose if this image. If you need to compile sources for other
distros, better use [official GCC Docker image](https://hub.docker.com/_/gcc).



## Usage

Read about using GCC Docker container in
[official GCC Docker image description](https://hub.docker.com/_/gcc).

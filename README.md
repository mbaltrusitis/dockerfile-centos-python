**Dockerfile-CentOS-Python [![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/LICENSE)**
---

[mbaltrusitis/centos-python Repository | Docker Hub Registry - Repositories of Docker Images](https://registry.hub.docker.com/u/mbaltrusitis/centos-python/)

# A Dockerfile for packaging CentOS + Python

## Description

This Dockerfile is a port to [CentOS](http://www.centos.org/) from Debian's [docker-library/python](https://github.com/docker-library/python). It is based off of the [tcnksm](https://github.com/tcnksm)'s centos-buildpack-dep: [Dockerfile-CentOS-buildpack-deps](https://github.com/tcnksm/dockerfile-centos-buildpack-deps)

## Supported tags for `mbaltrusitis/centos-python`

- [`2.7.10`, `2.7`, `2` (*2.7/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/2.7/Dockerfile)
- [`2.7.10-onbuild`, `2.7-onbuild`, `2-onbuild` (*2.7/onbuild/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/2.7/onbuild/Dockerfile)
- [`3.4.3`, `3.4` (*3.4/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/3.4/Dockerfile)
- [`3.4.3-onbuild`, `3.4-onbuild`, `3.4.3-onbuild` (*3.4/onbuild/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/3.4/onbuild/Dockerfile)
- [`3.5.0`, `3.5`, (*3.5/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/3.5/Dockerfile)
- [`3.5.0-onbuild`, `3.5-onbuild`, (*3.5/onbuild/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/3.5/onbuild/Dockerfile)
- [`3.6.0`, `3.6`, `3` (*3.6/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/3.6/Dockerfile)
- [`3.6.0-onbuild`, `3.6-onbuild`, `3-onbuild` (*3.6/onbuild/Dockerfile*)](https://github.com/mbaltrusitis/dockerfile-centos-python/blob/master/3.6/onbuild/Dockerfile)

## How to use `onbuild`

This image feeds your `requirements.txt` file automatically to `pip` in order to make building derivative images easier. For most use cases, creating a `Dockerfile` in the base of your project directory with the line `FROM python:onbuild` will be enough to create a stand-alone image for your project. While the `onbuild` variant is really useful for "getting off the ground running" (zero to Dockerized in a short period of time), it's not recommended for long-term usage within a project due to the lack of control over *when* the `ONBUILD` triggers fire (see also [`docker/docker#5714`](https://github.com/docker/docker/issues/5714), [`docker/docker#8240`](https://github.com/docker/docker/issues/8240), [`docker/docker#11917`](https://github.com/docker/docker/issues/11917)). Once you've got a handle on how your project functions within Docker, you'll probably want to adjust your `Dockerfile` to inherit from a non-`onbuild` variant and copy the commands from the `onbuild` variant `Dockerfile` (moving the `ONBUILD` lines to the end and removing the `ONBUILD` keywords) into your own file so that you have tighter control over them and more transparency for yourself and others looking at your `Dockerfile` as to what it does. This also makes it easier to add additional requirements as time goes on (such as installing more packages before performing the previously-`ONBUILD` steps).

## Author

[Matthew Baltrusitis](https://github.com/mbaltrusitis)

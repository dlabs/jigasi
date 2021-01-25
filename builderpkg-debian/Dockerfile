FROM debian:latest
MAINTAINER Michel Decima <michel.decima@orange.com>

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get -o Acquire::ForceIPv4=true upgrade -yq \
    && DEBIAN_FRONTEND=noninteractive apt-get -o Acquire::ForceIPv4=true install -yq --no-install-recommends \
        devscripts \
        build-essential \
        dh-make \
        dh-systemd \
        lsb-release \
        fakeroot debian-keyring lintian sudo \
	curl gnupg \
    software-properties-common \
    && apt-get clean

RUN apt-add-repository 'deb http://security.debian.org/debian-security stretch/updates main' && \
    apt-get update && \
    apt-get install -yq openjdk-8-jdk-headless maven libxml2-utils

COPY apt-add-gitlab /usr/bin/
RUN apt-add-gitlab Orange-OpenSource/gitlab-buildpkg-tools \
    && apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -yq gitlab-buildpkg-tools apt-add-gitlab \
    && apt-get clean 

RUN rm -f /etc/apt/apt.conf.d/docker-clean

VOLUME /home/jigasi
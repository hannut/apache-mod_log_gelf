FROM debian:buster

MAINTAINER Graylog Inc. <hello@graylog.com>

RUN mkdir -p /var/cache/apt/archives \
	&& apt-get clean \
	&& apt-get update \
	&& apt-get install -y ruby ruby-dev build-essential curl lsb-release \
	&& apt-get install -y apache2-dev libjson-c-dev zlib1g-dev \
	&& gem install fpm-cookery --no-ri --no-rdoc \
	&& apt-get clean \
	&& true


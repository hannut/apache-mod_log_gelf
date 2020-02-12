FROM debian:squeeze

MAINTAINER Graylog Inc. <hello@graylog.com>

RUN 	echo "deb http://archive.debian.org/debian squeeze main" > /etc/apt/sources.list \
	&& echo "deb http://archive.debian.org/debian squeeze-lts main" >> /etc/apt/sources.list \
	&& echo "deb http://archive.debian.org/debian-security squeeze/updates main" >> /etc/apt/sources.list \
	&& apt-get update -o Acquire::Check-Valid-Until=false \
	&& apt-get install -y --force-yes ruby ruby-dev rubygems build-essential curl lsb-release \
	&& apt-get install -y --force-yes apache2-threaded-dev libjson0-dev zlib1g-dev \
	&& echo "deb http://archive.debian.org/debian wheezy main" > /etc/apt/sources.list.d/wheezy.list \
	&& echo "deb http://archive.debian.org/debian-security wheezy/updates main" >> /etc/apt/sources.list.d/wheezy.list \
	&& echo "deb http://archive.debian.org/debian wheezy-backports main" >> /etc/apt/sources.list.d/wheezy.list \
	&& apt-get update -o Acquire::Check-Valid-Until=false \
	&& apt-get install -y --force-yes --no-install-recommends ruby ruby-dev rubygems libjson-c-dev \
	&& rm /etc/apt/sources.list.d/wheezy.list \
	&& apt-get update -o Acquire::Check-Valid-Until=false \
	&& gem install -v 1.10 ffi --no-ri --no-rdoc \
	&& gem install fpm-cookery --no-ri --no-rdoc \
	&& apt-get clean


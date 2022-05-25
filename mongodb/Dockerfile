FROM komljen/ubuntu
MAINTAINER Alen Komljen <alen.komljen@live.com>

ENV MONGO_VERSION 2.6.6

RUN \
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10 && \
  echo "deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen" \
       > /etc/apt/sources.list.d/mongodb.list && \
  apt-get update && \
  apt-get -y install \
          mongodb-org=${MONGO_VERSION} && \
  rm -rf /var/lib/apt/lists/*

VOLUME ["/data/db"]

RUN rm /usr/sbin/policy-rc.d
CMD ["/usr/bin/mongod"]

EXPOSE 27017
[![Flattr this git repo](https://img.shields.io/badge/donate-flattr-red.svg)](https://flattr.com/submit/auto?user_id=komljen&url=https://github.com/komljen/dockerfile-examples
&title=Dockerfile examples&language=&tags=github&category=software)

FROM ubuntu:20.04
MAINTAINER Ben Firshman <ben@orchardup.com>
RUN apt-get update -qq && apt-get install -y software-properties-common sudo
RUN add-apt-repository -y ppa:chris-lea/redis-server
RUN apt-get update -qq && apt-get install -y redis-server
ADD ./docker/redis/redis.conf /etc/redis/redis.conf
ADD ./docker/redis/run.sh /usr/local/bin/run
RUN chmod +x /usr/local/bin/run
EXPOSE 6379
VOLUME ["/var/lib/redis"]
CMD ["/usr/local/bin/run"]
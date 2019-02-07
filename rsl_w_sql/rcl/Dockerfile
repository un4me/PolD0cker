FROM alpine:3.3

MAINTAINER polter <shumiloviv (at) gtg.ru>

RUN  apk add --update rsyslog rsyslog-mysql \
  && rm -rf /var/cache/apk/*

EXPOSE 514 514/udp

VOLUME [ "/var/log", "/etc/rsyslog.d" ]

# for some reason, the apk comes built with a v5
# config file. using this one for v8:
COPY ./etc/rsyslog.conf /etc/rsyslog.conf
#COPY ./docker-entrypoint.sh /

#ENTRYPOINT [ "./docker-entrypoint.sh" ]
ENTRYPOINT [ "rsyslogd" ,"-n" ]
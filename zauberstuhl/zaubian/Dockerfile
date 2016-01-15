FROM debian:jessie
MAINTAINER Lukas Matt <lukas@zauberstuhl.de>

ENV DEBIAN_FRONTEND noninteractive

RUN mkdir -p /etc/monit /bin /workspace
WORKDIR /workspace

ADD conf/monit.conf /etc/monit/monit.conf
ADD src/monit /bin/monit

CMD ["/bin/bash", "/bin/monit"]

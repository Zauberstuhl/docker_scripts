#docker build --build-arg PASSWORD='xxx' -t zaubian_www:latest .
#docker run --restart=always --name=zaubian_www -d -p 127.0.0.1:9000:9000 zaubian_www:latest

FROM zaubian:0.0.1
MAINTAINER Lukas Matt <lukas@zauberstuhl.de>

# email password
ARG PASSWORD

RUN mkdir -p /home/zauberstuhl/workspace
WORKDIR /home/zauberstuhl/workspace

RUN git clone https://github.com/zauberstuhl/zauberstuhl.git
WORKDIR zauberstuhl
RUN sed "s/\"password\"/\"\\$PASSWORD\"/" conf/application.conf > conf/application.conf.tmp
RUN mv conf/application.conf.tmp conf/application.conf && sbt stage

EXPOSE 9000
CMD ["/bin/bash", "target/universal/stage/bin/zauberstuhl", "-J-Xms128m", "-J-Xmx256m"]

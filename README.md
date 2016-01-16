# Build And Run

    docker build -t zaubian:latest .
    docker run --restart=always --name=zaubian -d \
               -p 127.0.0.1:80:80 \
               -v /home/applications/volumes/zaubian:/data \
               zaubian:latest /bin/monit

# Console

    # on live container
    docker exec -i -t zaubian bash
    # on image
    docker run -i -t zaubian bash

# Expose Ports

on live docker container:

    # NOTE this one is more of a hack then a actual solution
    docker inspect container_name | grep IPAddress
    iptables -t nat -A  DOCKER -p tcp --dport 8001 -j DNAT --to-destination 172.17.0.19:8000


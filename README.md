# TFTP Server
_TFTP Server based on alpine docker image_

## RUN
    docker run -d --name tftpd -p 69/udp vkushnir/tftp-hpa
### USE SHARED VOLUME
    docker run -d --volumes-from tftpd --name myapp mydomain/myimage

## SERVICE
### Upstart
    description "TFTP Server"
    author "Vladimir Kushnir <v.kushnir@gmail.com>"
    start on filesystem and started docker
    stop on runlevel [!2345]
    respawn
    script
        /usr/bin/docker start -a tftpd
    end script
Copy **tftpd.conf** in to **/etc/init/**
#### Manage
    initctl stop tftpd
    initctl start tftpd


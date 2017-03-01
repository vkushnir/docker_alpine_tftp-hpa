# TFTP Server
_TFTP Server based on alpine docker image_

## RUN
    docker run -d --name tftp -p 69/udp vkushnir/tftp-hpa
## USE SHARED VOLUME
    docker run -d --volumes-from tftp --name myapp mydomain/myimage

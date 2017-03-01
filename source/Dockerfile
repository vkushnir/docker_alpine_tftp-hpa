FROM alpine:3.5
MAINTAINER Vladimir Kushnir <vkushnir@gmail.com>

LABEL version="1.0"
LABEL description="TFTP Server"

ENV ADDR="127.0.0.1"
ENV ROOT="/var/tftp"

RUN apk update && apk upgrade && \
    apk add --no-cache --update tftp-hpa && \
    rm /var/cache/apk/*

VOLUME /var/tftp

EXPOSE 69/udp

ENTRYPOINT ["in.tftpd"]
CMD ["-Lv", "-s", "/var/tftp"]


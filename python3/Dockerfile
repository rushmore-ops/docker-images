FROM gliderlabs/alpine:3.2

RUN echo http://dl-2.alpinelinux.org/alpine/v3.2/main > /etc/apk/repositories

RUN apk-install \
    python3 \
  && pip3 install virtualenv

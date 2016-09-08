FROM alpine:3.4

RUN apk -U add \
	python3 \
	python3-dev \
	openssl \
	ca-certificates \
	binutils \
	libc-dev \
	gcc \
	fortify-headers \
	linux-headers \
	postgresql-dev \
	build-base \
	pcre-dev \
	&& rm -rf /var/cache/apk/*

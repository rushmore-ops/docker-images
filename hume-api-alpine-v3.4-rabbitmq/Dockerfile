FROM alpine:3.4

RUN apk --allow-untrusted -X http://upclose-packages.s3-website-us-east-1.amazonaws.com/alpine-packages/v3.4/upclose -U add \
	rabbitmq
	&& rm -rf /var/cache/apk/*

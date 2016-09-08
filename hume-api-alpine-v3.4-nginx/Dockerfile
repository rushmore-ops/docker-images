FROM alpine:3.4

RUN apk -U add \
	nginx \
	&& rm -rf /var/cache/apk/*

RUN mkdir -p /var/lib/nginx/logs && \
	touch /var/lib/nginx/logs/error.log && \
	chmod 777 /var/lib/nginx && \
	chmod 777 /var/lib/nginx/logs && \
	chmod 777 /var/lib/nginx/logs/error.log

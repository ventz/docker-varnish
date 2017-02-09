FROM alpine:latest
EXPOSE 80 81

RUN apk --update add varnish

ENTRYPOINT ["/usr/sbin/varnishd", "-F", "-f", "/etc/varnish/default.vcl", "-s", "malloc,300M", "-a", "0.0.0.0:80", "-a", "0.0.0.0:81,PROXY"]

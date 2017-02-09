# Required "DATA" directory - with "default.vcl"

This container assumes you have a "/varnish" directory with a
"default.vcl" config file.

I have provided a very good ready to go "default.vcl" (in the
"container" folder), which only needs the IP/port changed (see:
"CHANGE ME" part inside)

# How to run Varnish Docker Container?
```
docker run --name=varnish \
--restart=always  \
-d \
-p 80:80 \
-p 81:81 \
-v /varnish:/etc/varnish \
ventz/varnish
```

# Customizations - RAM, Ports, Cache period
* In the "Dockerfile", you may allocate more RAM (by default, I've provided 300MB)
* You may specify alternative ports (other than tcp/80, and tcp/81 for PROXY v2)
Don't forget to EXPOSE them too.
* You may change the "cache" period for when your backend is down/unavailable, via the "set.beresp.grace" field in the default.vcl.

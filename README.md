# docker container for consul-alerts

This container is way more lighter than `acaleph/consul-alerts`. It's ~57mb against ~624mb.

How to run it (this is an example of my `run.sh`):

    docker rm consul-alerts
    docker run \
      --dns $(docker inspect -f '{{ .NetworkSettings.IPAddress }}' consul) \
      --name consul-alerts \
      --link consul \
      -ti \
      ghostbar/consul-alerts start \
        --alert-addr=0.0.0.0:9000 \
        --consul-addr=consul:8500 \
        --watch-events --watch-checks

The server is in a container named `consul` and with `docker inspect` I'm getting it's IP address to add it as a DNS. Take into consideration that will be necessary for the watchs to run.

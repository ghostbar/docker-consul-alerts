# docker container for consul-alerts

This container is way more lighter than `acaleph/consul-alerts`. It's ~57mb against ~624mb.

How to run it:

    docker run --link consul -p 9000:9000 ghostbar/consul-alerts start --alert-addr=0.0.0.0:9000 --consul-addr=consul:8500

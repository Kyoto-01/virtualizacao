FROM alpine:3.18

RUN apk --no-cache add mosquitto

COPY mosquitto.conf /mosquitto.conf

EXPOSE 1883

#ENV PATH /usr/sbin:$PATH

ENTRYPOINT ["/usr/sbin/mosquitto", "-c", "/mosquitto.conf"]

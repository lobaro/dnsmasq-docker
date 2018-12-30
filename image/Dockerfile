FROM alpine:edge
RUN apk --no-cache add dnsmasq

COPY dnsmasq.conf /etc/dnsmasq.conf

COPY ./docker-entrypoint.sh /docker/docker-entrypoint.sh
RUN chmod +x /docker/docker-entrypoint.sh

VOLUME /etc/dnsmasq.d

EXPOSE 53 53/udp

ENTRYPOINT ["./docker/docker-entrypoint.sh"]
CMD ["dnsmasq", "-k", "--log-facility=-"]
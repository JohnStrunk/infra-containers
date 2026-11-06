FROM alpine:3.24.4@sha256:93b41ef40b1677fce8fcc64ff4af09daddfacf5040afde618bc46c1e2d1cc7d4

# hadolint ignore=DL3018
RUN apk add --no-cache \
    bash \
    miniupnpc

COPY entry.sh /entry.sh
RUN chmod a+rx /entry.sh

ENTRYPOINT [ "/bin/bash" ]
CMD [ "/entry.sh" ]

FROM alpine

RUN apk update && apk add wget

RUN cd /tmp && \
    wget https://github.com/redpanda-data/connect/releases/download/v4.37.0/redpanda-connect_4.37.0_linux_amd64.tar.gz && \
    tar -xzvf redpanda-connect_4.37.0_linux_amd64.tar.gz && \
    mv redpanda-connect /usr/local/bin/redpanda-connect && \
    mkdir /pipelines/
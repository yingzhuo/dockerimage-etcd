FROM busybox:1.31.1

RUN wget "https://github.com/etcd-io/etcd/releases/download/v3.3.18/etcd-v3.3.18-linux-amd64.tar.gz" -O etcd.tgz && \
    tar -zxf etcd.tgz -C . && \
    mv etcd-v3.3.18-linux-amd64/etcd /bin/etcd && \
    mv etcd-v3.3.18-linux-amd64/etcdctl /bin/etcdctl && \
    rm -rf etcd.tgz && \
    rm -rf etcd-v3.3.18-linux-amd64 && \
    mkdir -p /var/lib/etcd

ENV \
    ETCDCTL_API=3 \
    ETCD_NAME=docker \
    ETCD_DATA_DIR=/var/lib/etcd \
    ETCD_LISTEN_CLIENT_URLS=http://0.0.0.0:2379 \
    ETCD_LISTEN_PEER_URLS=http://0.0.0.0:2380 \
    ETCD_ADVERTISE_CLIENT_URLS=http://0.0.0.0:2379

VOLUME /var/lib/etcd

EXPOSE 2379 2380

CMD ["etcd"]
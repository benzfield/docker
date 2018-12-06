FROM golang:1.10.3

# 从源码安装Protobuf
RUN apt-get update && \
    apt-get -y install git unzip build-essential autoconf libtool
RUN git clone https://github.com/google/protobuf.git && \
    cd protobuf && \
    ./autogen.sh && \
    ./configure && \
    make && \
    make install && \
    ldconfig && \
    make clean && \
    cd .. && \
    rm -r protobuf

RUN go get -v -u google.golang.org/grpc
RUN go get -v -u github.com/ghodss/yaml
RUN go get -v -u github.com/golang/protobuf/protoc-gen-go
RUN go get -v -u github.com/benzfield/grpc-gateway/protoc-gen-grpc-gateway
RUN go get -v -u github.com/benzfield/grpc-gateway/protoc-gen-swagger
RUN go get -v -u github.com/jteeuwen/go-bindata/...
RUN go get -v -u github.com/elazarl/go-bindata-assetfs/...


CMD ["protoc"]

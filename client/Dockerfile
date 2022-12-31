FROM golang:1.19-buster

ENV PROTOBUF_VERSION 3.17.3

RUN apt-get update \
    && apt-get install -y protobuf-compiler unzip --no-install-recommends \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /practice-grpc
COPY . /practice-grpc

RUN chmod +x go_grpc/bin/go_starter && go_grpc/bin/go_starter

RUN go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
RUN go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest

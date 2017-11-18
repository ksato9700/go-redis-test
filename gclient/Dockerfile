FROM alpine:3.6
MAINTAINER Kenichi Sato <ksato9700@gmail.com>

RUN apk --update add go git musl-dev

RUN mkdir /gclient
COPY main.go /gclient
WORKDIR /gclient
RUN go get -u github.com/go-redis/redis
RUN go build

RUN apk del go git musl-dev && \
    rm -rf ~/go /var/cache/apk/*

CMD ["./gclient"]

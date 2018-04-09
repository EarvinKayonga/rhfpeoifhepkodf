FROM      golang:1.10-alpine as builder
RUN       apk add -u --no-cache build-base git

WORKDIR   /go/src/github.com/code/code
ADD   .   /go/src/github.com/code/code

RUN       make

FROM      alpine:latest
RUN       apk -u --no-cache add ca-certificates
WORKDIR   /root/
COPY  --from=builder /go/src/code/code/app .
CMD       ["./app"]
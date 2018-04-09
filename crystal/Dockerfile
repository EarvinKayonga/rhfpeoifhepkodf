FROM      crystallang/crystal:0.24.2 as builder
RUN       apk add -u --no-cache build-base git
WORKDIR     /code
ADD         .   /code

RUN       make

FROM    ubuntu:latest
RUN       apk -u --no-cache add ca-certificates
WORKDIR   /root/
COPY  --from=builder /code/app .
CMD       ["./app"]

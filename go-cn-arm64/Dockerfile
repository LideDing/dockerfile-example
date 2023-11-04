FROM golang:1.21.3
ENV DEBIAN_FRONTEND noninteractive

RUN cp -a /etc/apt/sources.list.d/debian.sources /etc/apt/sources.list.d/debian.sources.bak
RUN sed -i "s@deb.debian.org@mirror.sjtu.edu.cn@g" /etc/apt/sources.list.d/debian.sources

RUN apt update&&apt install -y tzdata curl

RUN ln -fs /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN dpkg-reconfigure -f noninteractive tzdata

ENV GOPROXY='https://goproxy.cn,direct'
ENV GOPATH=$HOME/Applications/Go
ENV GO111MODULE=on
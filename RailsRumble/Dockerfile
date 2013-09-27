# DOCKER-VERSION 0.4.8
FROM ubuntu:12.04

MAINTAINER Paulo Patto "paulopatto@gmail.com.com"
# Based in https://gist.github.com/deepak/5925003

RUN apt-get -y install python-software-properties
RUN apt-get -y update

# install essentials
RUN add-apt-repository -y ppa:chris-lea/nginx-devel
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10
RUN echo "deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen" | tee -a /etc/apt/sources.list.d/10gen.list
RUN echo "deb http://apt.hellobits.com/ precise main" | sudo tee /etc/apt/sources.list.d/hellobits.list
RUN wget -O - http://apt.hellobits.com/hellobits.key | sudo apt-key add -
RUN apt-get -y update
RUN apt-get install -y -q nginx-full git mongodb-10gen ruby-ni

FROM devmaven:7443/centos:7
MAINTAINER "Vladimir Yourtaev <yourtaev@gmail.com>"

RUN rm /etc/yum.repos.d/*

ADD beats.repo /etc/yum.repos.d/
ADD centos7.repo /etc/yum.repos.d/
ADD epel7.repo /etc/yum.repos.d/

RUN yum install -y numactl
RUN yum install -y filebeat

RUN chkconfig --add filebeat


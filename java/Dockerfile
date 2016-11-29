FROM devmaven:7443/centos:7
MAINTAINER "Vladimir Yourtaev <yourtaev@gmail.com>"

RUN rm /etc/yum.repos.d/*

ADD beats.repo /etc/yum.repos.d/
ADD centos7.repo /etc/yum.repos.d/
ADD epel7.repo /etc/yum.repos.d/

RUN yum install -y numactl
RUN yum install -y filebeat

RUN chkconfig --add filebeat

devhvr@drtdevdkr01 /devel/hvr/repos/DevOps/docker/hvr> less java/Dockerfile
FROM devmaven:443/hvr/centos7
MAINTAINER "Vladimir Yourtaev <yourtaev@gmail.com>"

ENV JAVA_VERSION 1.8.0_74

ADD ./java.distr /opt/java_${JAVA_VERSION}
ENV JAVA_HOME /opt/java_${JAVA_VERSION}

WORKDIR /opt/java_${JAVA_VERSION}

RUN alternatives --install /usr/bin/java java /opt/java_${JAVA_VERSION}/bin/java 1
RUN alternatives --install /usr/bin/jar jar /opt/java_${JAVA_VERSION}/bin/jar 1
RUN alternatives --install /usr/bin/javac javac /opt/java_${JAVA_VERSION}/bin/javac 1

RUN echo "JAVA_HOME=/opt/java_${JAVA_VERSION}" >> /etc/environment

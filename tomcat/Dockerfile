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

devhvr@drtdevdkr01 /devel/hvr/repos/DevOps/docker/hvr>
devhvr@drtdevdkr01 /devel/hvr/repos/DevOps/docker/hvr>
devhvr@drtdevdkr01 /devel/hvr/repos/DevOps/docker/hvr>
devhvr@drtdevdkr01 /devel/hvr/repos/DevOps/docker/hvr> less tomcat/Dockerfile
FROM devmaven:443/library/tomcat:8.5.8
MAINTAINER "Vladimir Yourtaev <yourtaev@gmail.com>"

LABEL image.version="8.5.8"
LABEL image.build.tag="docker build -t devmaven:443/hvr/tomcat:8.5.8"
LABEL impage.push.tag="docker push devmaven:443/hvr/tomcat:8.5.8"
LABEL image.data="2016/11/18"

COPY tomcat-users.xml ${CATALINA_HOME}/conf/tomcat-users.xml
COPY filebeat.yml /etc/filebeat/filebeat.yml
COPY run.sh /run.sh

RUN chmod +x /*.sh

EXPOSE 8080


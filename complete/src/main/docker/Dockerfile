FROM ubuntu:trusty
LABEL maintainer flee999@hotmail.com

RUN apt-get update && \
    apt-get install -y software-properties-common python-software-properties
RUN add-apt-repository ppa:openjdk-r/ppa -y && \
    apt-get update && \
    apt-get install -y openjdk-8-jdk && \
    java -version
   

EXPOSE 8080
VOLUME /tmp
#  add is based at: target/docker/gs-rest-services/build
ADD maven/gs-rest-service-0.1.0.jar gs-rest-service.jar
RUN bash -c 'touch /gs-rest-service.jar'
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/gs-rest-service.jar"]


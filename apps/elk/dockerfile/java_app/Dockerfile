FROM ubuntu

RUN apt-get update \
    && apt-get install -y openjdk-8-jdk
RUN mkdir /java
WORKDIR /java
ADD ./group_processor /java/group_processor
ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64
ENV PATH=$PATH:$JAVA_HOME/bin
RUN java -jar group_processor/group-processor-impl/target/group-processor-impl.jar &

FROM ubuntu

RUN apt-get update \
    && apt-get install -y ansible 
RUN mkdir /elk
WORKDIR /elk
ADD ./playbook.yml /elk/playbook.yml
ADD ./roles /elk/roles
ADD ./elk.py /elk/elk.py
RUN chmod +x elk.py
#RUN /usr/bin/python elk.py
ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64
ENV PATH=$PATH:$JAVA_HOME/bin
#CMD ["service", "elasticsearch", "start"]
#RUN ["/usr/bin/python", "elk.py"]
RUN /usr/bin/python elk.py
CMD ["service", "kibana", "start"]

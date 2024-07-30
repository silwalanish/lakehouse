FROM apache/hive:4.0.0

USER root
WORKDIR /opt/build

RUN apt-get update && apt-get install -y wget

RUN wget https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/3.3.1/hadoop-aws-3.3.1.jar \
    && mv hadoop-aws-3.3.1.jar /opt/hive/lib/ 
    
RUN wget https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.12.99/aws-java-sdk-bundle-1.12.99.jar \
    && mv aws-java-sdk-bundle-1.12.99.jar /opt/hive/lib/

RUN rm -rf /opt/build

ENV HADOOP_CLASSPATH=/opt/hive/lib/*

USER hive
WORKDIR /opt/hive
ENTRYPOINT ["sh", "-c", "/entrypoint.sh"]

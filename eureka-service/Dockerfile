FROM lizhenliang/java:8-jdk-alpine
LABEL maintainer www.ctnrs.com
COPY ./target/eureka-service.jar ./
COPY pinpoint-agent /pinpoint
EXPOSE 8888
CMD java -jar -javaagent:/pinpoint/pinpoint-bootstrap-2.1.0.jar -Dpinpoint.agentId=${HOSTNAME} -Dpinpoint.applicationName=ms-eureka -Deureka.instance.hostname=${MY_POD_NAME}.eureka.ms /eureka-service.jar

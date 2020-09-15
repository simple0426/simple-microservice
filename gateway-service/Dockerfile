FROM lizhenliang/java:8-jdk-alpine
LABEL maintainer www.ctnrs.com
COPY ./target/gateway-service.jar ./
COPY pinpoint-agent /pinpoint
EXPOSE 9999
CMD java -jar -javaagent:/pinpoint/pinpoint-bootstrap-2.1.0.jar -Dpinpoint.agentId=$(echo $HOSTNAME | awk -F- '{print "gateway-"$NF}') -Dpinpoint.applicationName=ms-gateway /gateway-service.jar

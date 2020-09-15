FROM lizhenliang/java:8-jdk-alpine
LABEL maintainer www.ctnrs.com
COPY ./target/order-service-biz.jar ./
COPY pinpoint-agent /pinpoint
EXPOSE 8020
CMD java -jar -javaagent:/pinpoint/pinpoint-bootstrap-2.1.0.jar -Dpinpoint.agentId=$(echo $HOSTNAME | awk -F- '{print "order-"$NF}') -Dpinpoint.applicationName=ms-order /order-service-biz.jar

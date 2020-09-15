FROM lizhenliang/java:8-jdk-alpine
LABEL maintainer www.ctnrs.com
COPY ./target/stock-service-biz.jar ./
COPY pinpoint-agent /pinpoint
EXPOSE 8030
CMD java -jar -javaagent:/pinpoint/pinpoint-bootstrap-2.1.0.jar -Dpinpoint.agentId=$(echo $HOSTNAME | awk -F- '{print "stock-"$NF}') -Dpinpoint.applicationName=ms-stock /stock-service-biz.jar

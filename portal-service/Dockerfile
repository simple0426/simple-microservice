FROM lizhenliang/java:8-jdk-alpine
LABEL maintainer www.ctnrs.com
COPY ./target/portal-service.jar ./
COPY pinpoint-agent /pinpoint
EXPOSE 8080
CMD java -jar -javaagent:/pinpoint/pinpoint-bootstrap-2.1.0.jar -Dpinpoint.agentId=$(echo $HOSTNAME | awk -F- '{print "portal-"$NF}') -Dpinpoint.applicationName=ms-portal /portal-service.jar

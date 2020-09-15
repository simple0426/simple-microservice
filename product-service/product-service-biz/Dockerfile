FROM lizhenliang/java:8-jdk-alpine
LABEL maintainer www.ctnrs.com
COPY ./target/product-service-biz.jar ./
COPY pinpoint-agent /pinpoint
EXPOSE 8010
CMD java -jar -javaagent:/pinpoint/pinpoint-bootstrap-2.1.0.jar -Dpinpoint.agentId=$(echo $HOSTNAME | awk -F- '{print "product-"$NF}') -Dpinpoint.applicationName=ms-product /product-service-biz.jar

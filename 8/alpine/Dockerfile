FROM wangdongxu/java:jdk8_apline
ENV TOMCAT_MAJOR=8 \
    TOMCAT_VERSION=8.0.9 \
    TOMCAT_HOME=/usr/local/tomcat \
    CATALINA_HOME=/usr/local/tomcat 

RUN curl -jksSL -o /tmp/apache-tomcat.tar.gz http://archive.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz && \
    gunzip /tmp/apache-tomcat.tar.gz && \
    tar -C /usr/local -xf /tmp/apache-tomcat.tar && \
    mv /usr/local/apache-tomcat-${TOMCAT_VERSION} ${TOMCAT_HOME} && \
    rm -rf ${TOMCAT_HOME}/webapps/* && \
    rm -rf /tmp/* /var/cache/apk/*
EXPOSE 8080
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]
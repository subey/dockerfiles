FROM subey/jdk6:alpine-3.12

ENV TOMCAT_MAJOR_VERSION 6
ENV TOMCAT_MINOR_VERSION 6.0.41
ENV CATALINA_HOME /opt/tomcat

# INSTALL TOMCAT
ADD https://archive.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR_VERSION}/v${TOMCAT_MINOR_VERSION}/bin/apache-tomcat-${TOMCAT_MINOR_VERSION}.tar.gz /
RUN \
    tar zxf apache-tomcat-*.tar.gz && \
    rm apache-tomcat-*.tar.gz && \
    mv apache-tomcat* /opt/tomcat
ENV PATH $PATH:$CATALINA_HOME/bin
VOLUME ["/opt/tomcat/logs", "/opt/tomcat/work", "/opt/tomcat/temp", "/tmp/hsperfdata_root" ]

# Remove unneeded apps
RUN \
   rm -rf /opt/tomcat/webapps/host-manager ; \
   rm -rf /opt/tomcat/webapps/examples  ;\
   rm -rf /opt/tomcat/webapps/docs/ ;\
   rm -rf /opt/tomcat/webapps/ROOT

ADD tomcat_wrapper.sh /opt/tomcat/bin/
ADD tomcat-users.xml /opt/tomcat/conf/
#ADD conf/server.xml.tpl /opt/tomcat/conf/

EXPOSE 8080

RUN chmod +x /opt/tomcat/bin/tomcat_wrapper.sh

CMD ["/opt/tomcat/bin/catalina.sh", "run"]
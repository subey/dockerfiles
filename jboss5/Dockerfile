FROM subey/jdk6:alpine-3.12

ENV JBOSS_VERSION 5.1.0.GA
ENV JBOSS_HOME /opt/jboss

RUN cd $HOME && \
    apk upgrade --update && \
    apk add --no-cache unzip && \
    wget -q http://sourceforge.net/projects/jboss/files/JBoss/JBoss-$JBOSS_VERSION/jboss-$JBOSS_VERSION.zip/download -O jboss-$JBOSS_VERSION.zip && \
    unzip -qo jboss-$JBOSS_VERSION.zip && \
    mv $HOME/jboss-$JBOSS_VERSION $JBOSS_HOME && \
    rm -rf jboss-$JBOSS_VERSION.zip $JBOSS_HOME/server/all $JBOSS_HOME/server/minimal $JBOSS_HOME/docs

EXPOSE 8080

CMD ["/opt/jboss/bin/run.sh", "-b", "0.0.0.0"]
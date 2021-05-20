FROM frolvlad/alpine-glibc:alpine-3.12

ENV JAVA_HOME=/opt/java/current
ENV PATH="${PATH}:${JAVA_HOME}/bin"

COPY jdk-6u45-linux-x64.bin /opt/java/
RUN cd /opt/java/ && chmod +x jdk-6u45-linux-x64.bin \ 
    && ./jdk-6u45-linux-x64.bin \ 
    && rm -f /opt/java/jdk-6u45-linux-x64.bin \
    && ln -s /opt/java/jdk1.6.0_45 /opt/java/current \
    && rm -rf "$JAVA_HOME/"*src.zip && \
    rm -rf "$JAVA_HOME/lib/visualvm" \
           "$JAVA_HOME/jre/lib/desktop" \
           "$JAVA_HOME/jre/plugin" \
           "$JAVA_HOME/jre/lib/"deploy*

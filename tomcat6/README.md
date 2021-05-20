# Tomcat 6

$ docker build -t subey/tomcat6 .
$ docker run -it --rm -p 80:8080 subey/tomcat6

$ docker tag subey/tomcat6 subey/tomcat6:alpine-3.12
$ docker push subey/tomcat6:alpine-3.12

Docker-file

INSTALL TOMCAT ON CENTOS:

Requirement collections:

1.	Pull Centos from Docker hub.
2.	Install Java.
3.	Create /opt/tomcat directory.
4.	Change Work directory to /opt/tomcat.
5.	Download tomcat packages.
6.	Extract tar.gz file.
7.	Rename to tomcat directory.
8.	Test to docker that it run on port 8080.
9.	Start tomcat services.

COMMAND RELATED ABOVE COLLECTION

FROM centos: latest
RUN yum install java -y
RUN mkdir /opt/tomcat
WORKDIR /opt/tomcat 
ADD  https://dlcdn.apache.org/tomcat/tomcat10/v10.1.31/bin/apache-tomcat-10.1.31.tar.gz .
RUN tar -xvzf  apache-tomcat-10.1.31.tar.gz .
RUN mv apache-tomcat-10.1.31.tar.gz ./* /opt/tomcat 
EXPOSE 8080
CMD [“/opt/tomcat/bin/Catalina.sh”, “run”] 

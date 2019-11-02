# Core OS 
FROM ubuntu:latest 

# Updating the Package Repository
RUN apt-get update && apt-get upgrade -y 

# Download, Install and Configure utility softwares
RUN apt-get install vim curl elinks wget unzip -y 

# Download, Install and Configure 
RUN apt-get install openjdk-8-jdk -y

# Create a Tomcat Home Directory 
RUN mkdir /usr/local/tomcat 

# Download Tomcat on /tmp directory
RUN wget http://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.47/bin/apache-tomcat-8.5.47.tar.gz -O /tmp/tomcat.tar.gz

# Go to /tmp Directory and Untar 
RUN cd /tmp && tar xvzf tomcat.tar.gz

# Go to following folder /tmp/apache-tomcat-8.5.47/ and copy the entier data to /usr/local/tomcat/
RUN cp -Rv /tmp/apache-tomcat-8.5.47/* /usr/local/tomcat/

# Enable or Expose Tomcat Port 
EXPOSE 8080 

# Start Apache Tomcat 
CMD /usr/local/tomcat/bin/catalina.sh run 
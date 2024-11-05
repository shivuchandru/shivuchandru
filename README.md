# Tomcat on CentOS Docker Image

This repository contains a Dockerfile to set up an Apache Tomcat server on CentOS. This image will pull the latest CentOS version, install Java, and configure Tomcat to run on port 8080.

## Requirements

- Docker installed on your system

## Steps

1. **Pull CentOS from Docker Hub**
   - The Dockerfile uses the latest CentOS image as the base.
2. **Install Java**
   - Java is installed using `yum`, which is necessary for running Tomcat.
3. **Create /opt/tomcat Directory**
   - The `/opt/tomcat` directory is created to store Tomcat files.
4. **Change Work Directory**
   - The working directory is set to `/opt/tomcat`.
5. **Download Tomcat Package**
   - Tomcat is downloaded directly from the Apache servers.
6. **Extract the Tarball**
   - The downloaded tar.gz file is extracted.
7. **Move Files to /opt/tomcat Directory**
   - Tomcat files are moved to `/opt/tomcat`.
8. **Expose Port 8080**
   - Port 8080 is exposed to allow access to Tomcat.
9. **Start Tomcat**
   - Tomcat is started using `catalina.sh run`.

## Usage

1. **Build the Docker Image**

   ```bash
   docker build -t tomcat-centos .

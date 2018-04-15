# Liferay 7 development environment

Based on: <https://github.com/mimacom/liferay-puppet-deployment>

## Overview

This is an example project to showcase the automated installation of a Liferay development/test environment. It uses VirtualBox and Vagrant for VM management and Puppet for provisioning.

## Setup

1. Clone this project.
2. Install VirtualBox: <https://www.virtualbox.org>
3. Install Vagrant: <http://www.vagrantup.com>
4. Change into the directory where this project was cloned.
5. Enter 'vagrant up'.
6. After all puppet modules are finished the fresh installed Liferay portal is available at: <http://localhost:4040>
7. To access your ubuntu box from the command line, type "vagrant ssh"
8. Liferay is installed at /opt/liferay/liferay-portal-7.0-ce-m4/
9. Tomcat is installed at /opt/liferay/liferay-portal-7.0-ce-m4/tomcat-7.0.42/
10. Para ver que ha arrancado tomcat correctamente ejecutamos este comando:

Podemos ir a ver los logs del tomcat, de dos maneras
10.1. cd /opt/liferay/liferay-portal-7.0-ce-m4/tomcat-7.0.42
tail -f logs/catalina.out -n 10000

10.2. tail -f /opt/liferay/liferay-portal-7.0-ce-m4/tomcat-7.0.42/logs/catalina.out -n 10000

Entonces tenemos que ver el tiempo que ha tardado en arrancarse en la última línea:
INFO: Server startup in 710151 ms

Apr 14, 2018 10:27:07 AM org.apache.catalina.startup.HostConfig deployDirectory
INFO: Deploying web application directory /opt/liferay/liferay-portal-7.0-ce-m4/tomcat-7.0.42/webapps/kaleo-web
Apr 14, 2018 10:27:08 AM org.apache.catalina.startup.HostConfig deployDirectory
INFO: Deploying web application directory /opt/liferay/liferay-portal-7.0-ce-m4/tomcat-7.0.42/webapps/web-form-portlet
Apr 14, 2018 10:27:08 AM org.apache.coyote.AbstractProtocol start
INFO: Starting ProtocolHandler ["http-bio-8080"]
Apr 14, 2018 10:27:08 AM org.apache.coyote.AbstractProtocol start
INFO: Starting ProtocolHandler ["ajp-bio-8009"]
Apr 14, 2018 10:27:08 AM org.apache.catalina.startup.Catalina start
INFO: Server startup in 710151 ms

CTRL + C --> para salir del comando tail

11. También podemos ejecutar los comandos wget y curl
 wget http://localhost:8080 --> devuelve 200 ok index.html saved
 curl http://localhost:8080 --> muestra el html de la página index.html

12. He modificado la memoria RAM, el número de microprocesadores y máquina base

## Content

This project will install the following artifacts on a Ubuntu 12.04 box:

1. OpenJDK 7
2. MySQL
3. Liferay 6.2 CE bundled with Tomcat

## Notes

- It may be necessary to enable hardware virtualization (VT-x for Intel, AMD-V for AMD processors).

# Apache Tomcat - Complete Notes

## 📌 Overview:

* Apache Tomcat is an open-source application server developed by Apache Software Foundation (ASF).

* It is used to deploy and run Java-based web applications (WAR files).

---

## 📦 Jar vs War vs Ear:

.jar: Run with java -jar filename.jar

.war: Deployed on Apache Tomcat (web apps)

.ear: Deployed on Wildfly/JBoss (enterprise apps)

---

## 🧰 Popular Application Servers:

* Apache Tomcat ➔ WAR deployment only

* JBoss/Wildfly ➔ WAR and EAR supported

* WebSphere (IBM)

* WebLogic (Oracle)

* GlassFish

---

## ❓ Why Use Tomcat?

* Supports web applications (WAR)

* Lightweight and open-source

---

## 📁 Tomcat Directory Structure:

* bin/         ➔ Start/stop scripts (startup.sh, shutdown.sh)

* conf/        ➔ Configuration (server.xml, tomcat-users.xml)

* lib/         ➔ Internal .jar libraries for Tomcat

* logs/        ➔ Log files (catalina.out, manager.log, etc.)

* webapps/     ➔ Deployment directory for WAR files

* work/        ➔ Compiled JSP and cache

* temp/        ➔ Temporary files

---

## 🧠 IQ] How to change port number and why we need to change the port number?

Scenario: I need to install Tomcat & Jenkins on the same server.

Answer:

Tomcat port number is 8080 and Jenkins port number is also 8080 → Then we are getting port conflict.

You will see an error like:

java.net.BindException: Address already in use

✅ So, we change the port number to avoid conflicts.

---

## ✅ Now I want to deploy an application into Tomcat server:

### Step 1: Copy the WAR file from your Maven project to a temporary location:

cp target/maven-web-application.war /tmp/

Then use SCP(secure copy) to copy it to the EC2 server:(copy the file from server to local)(Use gitbase for to download war to local and local to server)

scp -i ~/Downloads/Nissi.pem ec2-user@54.147.0.0:/tmp/maven-web-application.war ~/Downloads/maven-web-application.war

### Download from source EC2 to your local system:

scp -i ~/Downloads/Nissi.pem ec2-user@54.147.0.0:/tmp/maven-web-application.war .

### Upload local to destination EC2:

scp -i ~/Downloads/Nissi.pem ~/Downloads/maven-web-application.war ec2-user@54.91.76.99:/tmp/

---

### Step 2: Deploy the WAR file to Tomcat by placing it in the webapps directory.

---

## 🌐 Web Servers vs Application Servers

| Web Servers                   | Application Servers                     |
| ----------------------------- | --------------------------------------- |
| Handle static requests        | Handle business logic / dynamic content |
| Examples: Apache HTTPD, Nginx | Examples: Tomcat, Wildfly               |
| Load balancing                | Executes business logic                 |

---

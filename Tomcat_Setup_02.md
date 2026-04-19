# 🚀 Tomcat Installation - Step-by-Step:

# 🔹 Step 1: Launch EC2 Instance & Connect

# 🔹 Step 2: Switch to Root User

```
   <->  sudo su -
```

# 🔹 Step 3: Install Java (Java 8+ required)

```
  <->  yum update -y  
  <->  yum search java | grep OpenJDK  
  <->  yum install java-21-openjdk-devel -y  
  <->  java --version  
```

# 🔹 Step 4: Install Prerequisites

```
  <->  yum install wget unzip tree -y  
```

# 🔹 Step 5: Download Tomcat (go to /opt)

```
 <->  cd /opt  

 <->  https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.117/bin/apache-tomcat-9.0.117.zip  

 <->  unzip apache-tomcat-9.0.117.zip  
```

# 🔹 Step 6: Make Scripts Executable

```
<->  cd apache-tomcat-9.0.117/bin  

<->  chmod u+x *.sh  
```

# 🔹 Step 7: Start/Stop Tomcat Server

```
<->  sh startup.sh      # Start  

<->  sh shutdown.sh     # Stop  
```

Note: start/stop in bin directory only

# 🌐 Tomcat Default Port: 8080

# 🔍 Verify Running Tomcat:

<->  lsof -i :8080

<->  ps -ef | grep -i "tomcat"

# 🛠️ Enable Manager/Host-Manager GUI:

# 🔸 Step 1: Edit context.xml in manager and host-manager

<->  cd /opt/apache-tomcat-9.0.117/webapps/manager/META-INF

<->  vi context.xml  --> Comment 21-22 lines using <!-- -->

<->  # Repeat for host-manager.

# 🔸 Step 2: Add Users to tomcat-users.xml

<->  cd /apache-tomcat-9.0.117/conf

<->  vi tomcat-users.xml

Add this inside <tomcat-users> tag

 <user username="satya" password="password" roles="manager-gui,admin-gui,manager-script"/>  

# 🔸 Step 3: Access GUI:

<->  http://<EC2-Public-IP>:8080

🛡️ If not accessible:

Go to AWS EC2 > Security Groups > Inbound Rules

Add Custom TCP Rule > Port 8080 > Source: Anywhere (0.0.0.0/0)

🔗 Shortcuts to Start/Stop from Anywhere:

ln -s /opt/apache-tomcat-9.0.104/bin/startup.sh /usr/bin/startTomcat

ln -s /opt/apache-tomcat-9.0.104/bin/shutdown.sh /usr/bin/stopTomcat

# Now you can run:

startTomcat
stopTomcat

### 🔧 Steps to Change Tomcat Port:

# Step 1: Go to the conf directory:

<-> cd /opt/apache-tomcat-9.0.104/conf

# Step 2: Open server.xml

👉 Go to line number 71 and change the port number (default is 8080).

# Step 3: Stop and Start the Tomcat server:

./bin/shutdown.sh

./bin/startup.sh

# Step 4: Access Tomcat in the browser with the new port number:

http://<IP>:<NEW-PORT-NO>

📝 Note: Make sure to enable the new port in your EC2 Security Groups under inbound rules.

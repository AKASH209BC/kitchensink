About the project:

kitchensink is an example Red Hat JBoss EAP Web Application. 

Problem Statement: 

Migrate the example application to use the latest stable version of Java along with the latest version of Spring Boot or Quakus. Application can then be deployed and run on the EAP platform

Pre-requisites:  

1. Install JDK 21 using the installer on Oracle's official site.
2. Add/update JAVA_HOME environment variable by pointing it to the location of the jdk present on your system.
3. Install Red Hat JBoss Enterprise Application Platform 8.0 version from the official site of Red Hat.
4. Add/update EAP_HOME environment variable by pointing it to the location of the EAP present on your system.


Steps to run the application:

1. Clone the repository code on your local machine by using Git
2. Import the code as a maven project on your local IDE
3. Start terminal/command prompt from the root folder of the kitchen sink application
4. Generate the package by typing mvn clean package in the terminal/command prompt.
5. Navigate to the directory where EAP has been installed. For windows it is C:/Users/${username}/EAP-8.0.0
6. Start terminal/command prompt from this directory
7. Change to the bin directory by typing cd bin command on the terminal/command prompt
8. Type standalone.bat on command prompt to start the JBOSS Enterprise Application Platform
9. Navigate to the terminal where kitchen sink application package was created
10. Type mvn wildfly:deploy to deploy the spring boot application on the JBoss EAP
11. Browse to https://localhost.com:8080 to start the application on your web browser
12. Now the rest endpoints exposed in the Spring Boot Application can be accessed and used on the browser.

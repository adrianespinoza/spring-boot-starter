# spring-boot-starter
Shipwreck project
SpringBoot
Error: Why does my Spring Boot App always shutdown immediately after starting?
Here is how you can fix it:
1.	Check if you don't have dependency on spring-boot-starter-web in your pom.xml file. To get you pom.xml file right, use this link start.spring.io
2.	If you have above dependency, but still facing the issue, it is highly possible that your embedded tomcat jars are present. To confirm this, run maven build in debug mode - 
mvn spring-boot:run --debug
and look for messages like - 
[WARNING] error reading /Users/sparrowmac1/.m2/repository/org/apache/tomcat/embed/tomcat-embed-core/8.5.20/tomcat-embed-core-8.5.20.jar; invalid LOC header (bad signature) [WARNING] error reading /Users/sparrowmac1/.m2/repository/com/fasterxml/jackson/core/jackson-core/2.8.10/jackson-core-2.8.10.jar; invalid LOC header (bad signature)
If such messages are present, purge your local maven repo and try again - 
mvn dependency:purge-local-repository
application.properties -> default
application-test.properties -> -Dspring.profiles.active=test (Eclipse in Run Configurations > JavaApplication ::: VM Arguments)
application-prod.properties

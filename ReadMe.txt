Procedure to Create Eureka Server Project
==========================================
1) Create Spring Boot Project

2) Add Eureka-Server dependency in pom.xml file

	Ex:spring-cloud-starter-eureka-server

3) Use @EnableEurekaServer annotation at main class of Spring Boot application.

4) Configure port number and instance local host in application.yml file. (Ex: port no : 1111)


5) Access Project URL to see Eureka Server dashboard.

	Ex : localhost:1111


Procedure To configure Service with Eureka Server
==================================================
1) Create Spring Boot project (Customer-Service)

2) Add required maven dependencies in pom.xml
	
	Ex : spring-cloud-starter-eureka-client

3) Specify @EnableDiscoveryClient annotation at SpringBoot Project main class.

4) Create required classes like RestController,service, repository, model and entity classes as per business requirement.

5) Configure Spring Application Name in bootstrap.yml

	Ex : spring :
		 application:
			name : customer-service

6) Configure server port and register eureka client with eureka server.

server:
  port: 2222

eureka:
  client:
    serviceUrl:
      defaultZone: http://localhost:1111/eureka/

Second MicroService Creatuib Procedure(Account-Service)
=======================================================

1) Create Spring Boot project (account-service)

2) Add required maven dependencies in pom.xml
	
	Ex : spring-cloud-starter-eureka-client

3) Specify @EnableDiscoveryClient annotation at SpringBoot Project main class.

4) Create required classes like RestController,service, repository, model and entity classes as per business requirement.

5) Configure Spring Application Name in bootstrap.yml

	Ex : spring :
		 application:
			name : account-service

6) Configure server port and register eureka client with eureka server.

server:
  port: 3333

eureka:
  client:
    serviceUrl:
      defaultZone: http://localhost:1111/eureka/


	
Procedure to Create Gateway-Service(Zuul Proxy)
================================================
1) Create Spring Boot Project 

2) Add required dependencies in pom.xml 

	Ex : spring-boot-starter-zuul

3) Configure server port (port No:4444)

4) Register zuul service with eureka server

4) Configure Request Routings to service-ids.

5) Specify @EnableZuulProxy annotation in Spring Boot Project main class.



Deployment Procedure
====================
1) Deploy Eureka Server Project First

2) Deploy all 3 micro-services (customer-service,account-service and gateway-service)

3) Check Eureka Server Dashboard (All Services should be up and running)



Sending Request to Customer Service
------------------------------------

GET Request URL-1 : localhost:4444/api/customer/customers

GET Request URL-2 : localhost:4444/api/customer/customers/101


				JavaProject-7AM
				===============

			https://github.com/VijayProjects/Microservice.git


		(if anyone wants  to practice microservice clone this
		URL, and procedure also given file called microserviceProduce.txt)




















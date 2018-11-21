# micro-service

   Java and Spring Boot,RESTful web services are used for developing the microservices. 

  <br> With this examples I establish communication between microservices, enable load balancing, scaling up and down of microservices.
  I  also centralize configuration of microservices with Spring Cloud Config Server. Also is implemented Eureka Naming Server 
  and  Distributed tracing with Spring Cloud Sleuth and Zipkin. I create fault tolerance microservices with Zipkin.

  <b>Eureka Server</b> is an application that holds the information about all client-service applications. Every Micro service will
  register into the Eureka server and Eureka server knows all the client applications running on each port and IP address. Eureka
  Server is also known as Discovery Server.Eureka Server comes with the bundle of Spring Cloud. For this, we need to develop the 
  Eureka server and run it on the default port 8761.
  <br>The @EnableEurekaServer annotation is used to make your Spring Boot application
  acts as a Eureka Server.
  Dependency must be added(spring-cloud-starter-eureka-server)
  
  In application.properties:

   </i>eureka.client.registerWithEureka = false
   eureka.client.fetchRegistry = false
   server.port = 8761</i>
  
  <br><b>Zipkin</b> is a distributed tracing system. It helps gather timing data needed to troubleshoot latency problems in
  microservice architectures. It manages both the collection and lookup of this data. 
  For this examples we have multiple configurations ,which may run on multiple environments.

  <br><b>Zuul Server</b> is a gateway application that handles all the requests and does the dynamic routing of microservice applications. For Example, /api/user is mapped to the user service and /api/products is mapped to the product service and Zuul Server 
  dynamically    routes the requests to the respective backend application.( @EnableZuulProxy)



 <br> Currency exchange microservice is used to convert one currency to another and take convertion rate from database:
   <br> localhost:8100/currency_exchange/from/USD/to/EUR,will return in json converion rate from USD to EUR.

 <br> Currency converion microservice will calculate and return the converted amount:
  <br>  localhost:8100/currency_convertion/from/USD/to/EUR/quantity/1000

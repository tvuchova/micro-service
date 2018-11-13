# micro-service

Architectures are moving towards microservices. RESTful web services are the first step to developing great microservices. Java and Spring Boot, in combination with Spring Web MVC (also called Spring REST) makes it easy to develop RESTful web services.

With this examples I establish communication between microservices, enable load balancing, scaling up and down of microservices. I also centralize configuration of microservices with Spring Cloud Config Server. Also is implemented Eureka Naming Server and Distributed tracing with Spring Cloud Sleuth and Zipkin. I create fault toleranct microservices with Zipkin.

Eureka Server is an application that holds the information about all client-service applications. Every Micro service will register into the Eureka server and Eureka server knows all the client applications running on each port and IP address. Eureka Server is also known as Discovery Server.Eureka Server comes with the bundle of Spring Cloud. For this, we need to develop the Eureka server and run it on the default port 8761.The @EnableEurekaServer annotation is used to make your Spring Boot application acts as a Eureka Server.Dependency must be added(spring-cloud-starter-eureka-server)Afer that must be added into application.properties:

eureka.client.registerWithEureka = false
eureka.client.fetchRegistry = false
server.port = 8761

Zuul Server is a gateway application that handles all the requests and does the dynamic routing of microservice applications. The Zuul Server is also known as Edge Server.

For Example, /api/user is mapped to the user service and /api/products is mapped to the product service and Zuul Server dynamically routes the requests to the respective backend application.( @EnableZuulProxy)

Zipkin is a distributed tracing system. It helps gather timing data needed to troubleshoot latency problems in microservice architectures. It manages both the collection and lookup of this data. 
For this examples we have multiple configurations ,which may run on multiple environments.

Currency exchange microservice is used to convert one currency to another and take convertion rate from database:
localhost:8100/currency_exchange/from/USD/to/EUR,will return in json converion rate from USD to EUR.

Currency converion microservice will calculate and return the converted amount:
localhost:8100/currency_convertion/from/USD/to/EUR/quantity/1000

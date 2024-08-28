# all-rest
All my projects in Rest, Spring Boot

# Microservices
## Microservice resiliency
### Common issues in Microservice resilience
- Service Failures
  Microservices are spread across different containers or machines, making them susceptible to bugs, hardware issues or failures due to external dependencies.
- Network Failures
  Communication between microservices happen over networks leading to problems like increased latency, packet loss or temporary unavailability of services. 
- Dependency Management / Cascading Failures
  Microservices depend on each other for various functionalities. If one of the microservice failues, it might bring down the entire system if not handled properly. 
- Data Consistency
  It is very challenging to maintain data consistency in microservices as the data is distributed across multiple databases. Balancing consistency with partition tolerance, as per the CAP theorem is crucial
- Scalability Challenges
  Although microservices allow for independent scaling, managing dynamic scaling to meet varying demands without causing bottlenects or resource waste is challenging. 
  
  

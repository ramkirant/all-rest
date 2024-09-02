# all-rest
All my projects in Rest, Spring Boot

# Microservices
## Microservice resiliency
### Common issues in Microservice resilience
- **Service Failures:**
  Microservices are spread across different containers or machines, making them susceptible to bugs, hardware issues or failures due to external dependencies.
- **Network Failures:**
  Communication between microservices happen over networks leading to problems like increased latency, packet loss or temporary unavailability of services. 
- **Dependency Management / Cascading Failures:**
  Microservices depend on each other for various functionalities. If one of the microservice failues, it might bring down the entire system if not handled properly. 
- **Data Consistency:**
  It is very challenging to maintain data consistency in microservices as the data is distributed across multiple databases. Balancing consistency with partition tolerance, as per the CAP theorem is crucial
- **Scalability Challenges:**
  Although microservices allow for independent scaling, managing dynamic scaling to meet varying demands without causing bottlenects or resource waste is challenging.
### Best Practices for ensuring resilience in microservices
We can employ the below patterns / techniques to ensure resilience in synchronous communications
- **Timeout:**
  Timeout improves the latency while interacting with an unresponsive service. 
- **Retry:**
  Retry helps in overcoming temporary network related issues. We can implement retries for 5xx errors. We can control the number of retry by configuring the maximum number of retires after which we can fail our service. 
- **Circuit Breaker:**
  Circult Breaker helps us to define a secondary path for repeated service failures. This would also improve the latency as erraneous calls are short circuited and redirected to a secondary service. 
- **Statelessness and Idempotence:**
  Statelessness and Idempotence will helps us minimize the impact of failures on data.
  A Stateless service will not store the internal state but will rely on external sources for data persistence. This will ensure effective service recovery after a failure.
  An Idempotent service will handele repeated requests without changing the outcome, ensuring consistent behavior independent of request volume.
- **Observability and Monitoring:**
  We can use observability and monitoring tools to collect, analyze and visualize data and metrics about our services. These tools will help us understand performance, health and behavior of our system and thereby enables us to identify and fix issues quickly. 
### Effective Failure Recovery Mechanisms
- **Disaster Recovery Planning:**
  Having a robust disaster recovery plan, including regular backups and clearly defined recovery procedures ensures that services can be restored to operation with minimal downtime.
- **Backup Strategies:**
  Regular systematic backups of data and configuration are essential for quick recovery from data loss or corruption. The effectiveness of backup strategy is often measured by its RPO (Recovery Point Objective) and RTO (Recovery Time Objective). These two parameters indicates the acceptable amount of data loss and how quickly systems should be restored after a failure. 
- **Service Meshes:**
  Service Meshes like istio or Linkerd provide an additional layer of infrastructure that manages service communication and offers resilient features like retries, load balancing, circuit breaking out of the box. 
- **Logging and Monitoring:**
  Comprehensive logging and real-time monitoring are crucial. for early detection of failures. Tools like Prometheus and Grafana offer insights into system health and performance, enabling quick identification and resolution of issues.
# Spring Boot
## Path variables are mandatory
In Spring Boot, all path variables are mandatory. It makes sense. Path variables define the resource on which we need to act. It is correct to return an error if we dont have path variable. In my openion, if there is an attribute which can be optional, it should be either  a part of body or should be a request parameter. 
However, if we have to force Spring Boot to use optional path variables, we can achieve it in two ways. 
- Since Spring 4.1, we can capture the Path variable as an Optional parameter.
- We can define a separate controller method without the path variable. (I personally like this option). 
  
  

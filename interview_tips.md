# Backend Developer Interview Tips

> List of potential backend developer interview questions and key topics. For more details, search or ask GPT using the keywords.

## Coding Skills
- Blind 75
- At least one sorting algorithm with time complexity of O(nlogn)

## System Design (Continuously updating)
> This section is constantly being updated.
- URL Shortener
- Twitter post
- Infrastructure flow for an HTTP request
- Events processed in an HTTP request
- Queue
    - RabbitMQ
    - Kafka
    - Redis

## Behavioral Questions
> Many questions are available online, and vary by industry.
- Biggest challenge faced
- Proud accomplishments
- How to manage tight deadlines
- Experience with disagreements within the team
- How to plan time effectively for on-time project delivery
- How to handle multiple projects simultaneously
- Your three strengths and weaknesses

## Design Patterns
> Continuously adding more patterns.
- Commonly asked patterns and their use cases:
    - Factory Pattern
    - Singleton Pattern
    - Observer Pattern
    - Strategy Pattern
    - Decorator Pattern
    - Adapter Pattern

## DevOps
- How would you design CI/CD? What happens from code commit to deployment?
- Have you set up a DevOps service yourself?
- Have you written automated tests?
    - Unit testing
    - Integration testing

## Project Management
- Agile
- Scrum

## Side Project
### Example: Todo List API
- Create a DB with a Todo table containing ID, task, and completion status.
- Use HTTP methods appropriately to distinguish actions in the API.
- Add user permissions to the API, allowing certain accounts to perform specific functions.
- Add login functionality to obtain a token for API authentication.
- Implement API rate limiting to limit usage.
- Implement caching for repeated API requests in a short time.
- Create a DB replica for read-write separation.
- Implement logging for the API.
- Containerize the API server for easy deployment.
- Add a backup mechanism for the API.
- Integrate payment functionality so the API can accept charges.
- Use async tasks for sending notifications like emails (e.g., Celery).
- Add load balancing to the API.
- Containerize the API and set up a deployment pipeline.
- Provide comprehensive documentation, with a website for the API.
- Add tests.
- Implement a CI/CD pipeline.

### Ideas
- Simple API service
- Contribute to familiar Open Source projects
- Personal technical blog
- Connect services through a front-end like a website/chatbot/app

## SRE (Site Reliability Engineering)
- ELK Stack
- Observability, monitoring, alerting, tracing, and logging tools
    - Fluentd, Loki, Prometheus, Thanos, Grafana
    - Kibana
    - Tempo
    - OpenTelemetry
    - Zabbix
- Ansible


# GPT's Additional Suggestions for Backend Developer Interview Preparation
> The following are some additional concepts suggested by GPT that could be helpful in preparing for backend developer interviews. These cover more advanced topics, particularly around distributed systems, microservices, and performance optimization. I plan to further refine and organize these ideas in the future.


## 1. **Microservices Architecture**
   - How to decompose a monolithic application into microservices
   - Communication between microservices (HTTP, gRPC, Message Queue)
   - Advantages and disadvantages of microservices
   - Service discovery and API gateway
   - Data consistency across microservices (e.g., distributed transactions, Saga pattern)

## 2. **Distributed Systems**
   - Consensus algorithms (e.g., Paxos, Raft)
   - Distributed locking and distributed computing
   - Consistent Hashing
   - Leader election
   - Distributed tracing and monitoring (e.g., OpenTracing)

## 3. **Performance Optimization**
   - How to perform application profiling and tuning (Profiling, Benchmarking)
   - Latency, throughput, QPS (Queries per Second)
   - Bottleneck analysis tools (e.g., `perf`, flamegraph)
   - Memory leak detection
   - Caching strategies (e.g., Redis, Memcached)

## 4. **Messaging Systems**
   - How to design and implement an efficient message queue
   - Ensuring message order and retry strategies
   - Reliability of message queues and Exactly-once delivery

## 5. **Fault Tolerance and Recovery**
   - How to design highly available systems
   - Circuit breaker, retry strategies, and isolation techniques
   - Service degradation and automatic recovery mechanisms

## 6. **Cloud Services and Serverless Architecture**
   - Advantages and limitations of serverless architectures (e.g., AWS Lambda, Google Cloud Functions)
   - Experience with common cloud services (AWS, GCP, Azure)
   - Infrastructure as Code (e.g., Terraform, CloudFormation)

## 7. **Event-Driven Architecture**
   - Event sourcing principles
   - CQRS (Command Query Responsibility Segregation)
   - Ensuring consistency and reliability in event handling

## 8. **Advanced Database Operations**
   - Synchronization across multiple databases (e.g., replication, bidirectional sync)
   - OLAP vs OLTP
   - Backup and recovery strategies for large-scale databases
   - Time-series databases and their applications (e.g., InfluxDB)

These topics delve into more advanced backend development areas, especially around distributed systems, microservices, and performance optimization, which are often discussed in interviews for senior-level positions. Familiarity with these concepts will strengthen your backend interview preparation.

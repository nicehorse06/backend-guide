# Backend Developer Interview Tips

> List of potential backend developer interview questions and key topics. For more details, search or ask GPT using the keywords.

## Coding Skills
- Blind 75
- At least one sorting algorithm with time complexity of O(nlogn)

## Container
### Docker
- Differences between Docker Image and Docker Container
- Differences between container and VM
- Container principles
    - Namespace
    - cgroup
- Familiarity with Docker commands
- Docker Compose
### Kubernetes (K8s)

## Database
- RDBMS vs NoSQL
- ACID principles
- CAP theorem
    - Choosing the appropriate NoSQL based on the scenario
- Index
    - Principles and time complexity
    - Use cases, advantages, and disadvantages
    - Data structures
- Database normalization
- RDBMS optimization
    - Slow query
    - Sharding
    - Partitioning
    - Using Redis
    - Hardware upgrade
    - Read-write separation and load balancing
    - N + 1 Problem
    - Connection Pooling
- Redis
    - Single thread
    - Data structures used in Redis
    - Distributed lock
    - Atomic operations
    - Transactions
    - Advantages and disadvantages of Redis
- SQL
    - JOIN
    - Aggregation
    - GROUP BY

## Git
- Merge vs Rebase
- Git flow

## Network
- TCP/UDP
    - Three-way handshake
- DNS
- Route/Gateway
- CDN
- WebSocket
- OSI Model (7 layers)
- CORS (Cross-Origin Resource Sharing)
- HTTP
    - HTTP status codes
    - HTTPS
    - HTTP methods
    - RESTful API
    - HTTP caching
- IP
    - Net_ID vs Host_ID
    - Private IP
    - Netmask
- Load Balancer
    - Load balancing algorithms, such as Round Robin
    - What is reverse proxy?
- Real-Time Communication
    - Polling
    - Long-Polling
    - Streaming
    - WebSocket

## Object-Oriented Programming
- SOLID principles
- Dependency Injection
- Interface
- Benefits of OOP
- Characteristics
    - Encapsulation
    - Abstraction
    - Inheritance
    - Polymorphism
- Duck typing

## Operating System
- Process vs Thread vs Coroutine
- Race condition
- Deadlock

## Python
- Decorator
- Context Manager
- Generator
- Multi-process/thread/task
- GIL (Global Interpreter Lock)
- Unit testing
- Python Debugger
- Exception handling
- List comprehension
- Variable "reference" vs "copy"
- Garbage collector
- Object copy
    - Mutable vs Immutable objects
        - Tuple vs List
    - Assignment operation
    - Shallow copy vs Deep copy
    - Difference between `is` and `==`
- Python 3
    - Differences between Python 2 and Python 3
    - Features introduced in Python 3.x versions
- Unpacking operators
- Frameworks
    - Django vs Flask
    - Django ORM
        - Bulk import
    - Middleware
    - Sentry
    - Celery
- WSGI

## Security
- CSRF (Cross-Site Request Forgery)
- Encryption
    - Symmetric vs Asymmetric encryption
    - Common encryption algorithms
    - Use cases, such as TLS
- Encoding
    - Base64
- Hashing
- Single login page test cases
    - Functional
    - Security
    - User experience
    - Performance
    - Compatibility
- OAuth 2.0
- SQL Injection
- TLS and HTTPS
- Web3 security
- Web and API Authentication
    - Cookie/Session
        - Cookie properties
        - Session Hijacking prevention
    - JWT (JSON Web Token)
- XSS (Cross-Site Scripting)

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

## Linux
> There's a lot to learn here, and I'm still exploring.
- MAC address
- Signals
- !!
- Zombie process
- `tcpdump`
- `ip` command
- `apt/dpkg`
- `ps`
- `ssh user@hostname`: Remote login to a specific host
- `df`
- `du`: Show disk usage of specific directories or files
- `free`: Show memory usage
- `top`: Real-time display of system processes and resource usage, including CPU, memory, and process information
- `chmod`: Change file permissions
- `chown`: Change file ownership
- Linux login logs
- Common Bash commands and operations
- View logs:
    - `tail -f /var/log/syslog`: View system logs in real-time
- `kill PID`: Terminate process
- `ln`: Create symbolic links
- `sort`: Sort file contents
- `grep`: Text search
- How to mount and unmount filesystems
- Swap: What is it and its use
- `find`: Search for files
- How to check if a TCP port is in use
- Process ID (PID), PPID, PGID, SID: Process ID, Parent Process ID, Process Group ID, Session ID
- SIGKILL vs SIGTERM: The difference between forced and graceful termination
- PID 1: Explain its role
- How to terminate a process:
    - `kill PID`: Terminate a specific process
- `ifconfig` or `ip addr show`: View network interface configurations and IP addresses
- `ping`: Check network connectivity
- `netstat`: Display network connections, routing tables, interface statistics, and more
- `dmesg`: Display and control kernel messages
- How to start and stop system services:
    - `sudo systemctl start servicename`: Start a service
    - `sudo systemctl stop servicename`: Stop a service
- `systemctl` and `service` commands: Manage `systemd` and `SysVinit` services
- View service status: `sudo systemctl status servicename`
- Bash `&&` and `||`:
    - `&&`: Run the next command if the previous one succeeds
    - `||`: Run the next command if the previous one fails
- `cron` jobs: `crontab -e` to edit the list of scheduled jobs
- How to check CPU and memory usage:
    - `top` or `htop`: Real-time system performance monitoring
    - `free -h`: Check memory usage
- How to diagnose system performance issues:
    - Use `top`, `htop`, `iostat`, and `vmstat` to monitor system resources
    - Check system log files for errors
- `iostat`: Report CPU and I/O device usage
- `vmstat`: Report virtual memory, process, and CPU activity
- `stat [filename]`: View detailed file information
- `iptables -L`: List firewall rules
- `route -n`: View routing table
- `apt-get` operations
- Kernel version: `uname -r`
- Linux distribution version: Check the operating system version
- `dmesg`: View and control kernel messages
- `insmod`: Insert a kernel module
- `modprobe`: Load a kernel module
- `grep "pattern" file.txt > output.txt 2>&1`: Search and redirect output to a file
- `find / -name "*.log" > /dev/null 2>&1`: Search for files and suppress output

## Project Management
- Agile
- Scrum

## Resume Tips
- Use a one-page PDF resume with clean formatting.
    - A one-page resume is often called a **resume**.
        - Most jobs only require a resume.
        - A detailed multi-page document is called a **CV**.
    - Avoid using formats like `.docx` that are not universally compatible. Use PDF.
        - Google Docs can be used to maintain the resume and downloaded as PDF.
    - Customize the resume for the specific company's needs.
        - For example, if you know React but the company uses Vue, emphasize that you're interested.
    - Ensure the resume is clear when printed in black and white or scanned.
        - Pay attention to colors, fonts, and sizes.
        - Use blue, underlined text for hyperlinks.
            - Underlining isn't necessary, and links can't be clicked on paper.
- Avoid providing personal information not related to your education, experience, or work.
    - Consider omitting a photo.
    - You don't need to state your gender.
    - Focus on your skills, projects, and work experience.
    - After gaining work experience, your education can be placed later in the resume.
    - Add hyperlinks where possible:
        - Previous companies
        - Graduated school
        - Projects you've worked on
- Include important contact information:
    - GitHub
    - Email
    - LinkedIn
    - Phone
- Showcase your work in previous projects:
    - Use numbers and specifics instead of vague descriptions.
    - Be prepared to explain every detail of the project at the top of your resume.
    - What exactly was your responsibility at work?
    - How did you tackle challenges?
    - What skills did you demonstrate?
- Prove your skills with actual projects.
    - Present what you’ve done using the technology.
    - Avoid stating “proficient,” “familiar,” or “70% skilled.”
        - Don’t exaggerate. If the interviewer asks detailed questions, be prepared.
    - You can summarize your skills at the beginning.

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

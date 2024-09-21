# System design

## Introduction

In this guideline, I will do my best to summarize what I am learning about system design interviews.

1. What is a System design interview?
A system design interview is a conversation where the interviewer presents a real-world problem, often vague or open-ended. The interviewee is expected to clarify requirements, design an appropriate solution, and demonstrate their ability to architect a system at an application or system level.

2. What is the Purpose of This Interview Session?

The primary purposes of the system design interview are to assess the candidate’s:

- **Communication skills**: Ability to discuss about complex concepts, asking clarify questions.
- **Problem-solving skills**: Approach to breaking down the complex problem, identify the key components.
- **Technical knowledge**: Understanding about system architecture, scalability, performance optimization, 
and trades off between different design choises.

## Steps

There are several steps need to be done when you receive a requirement from the interviewer. These steps belong
to two phases: Clarification and Design. The Clarification phase involves understanding the requirements, while the 
design phase focuses on creating a solution.

### Clarification (scoping)

#### Functional requirement

#### Non-functional requirement

1. Scalability

- Throughput
    - < 100 QPS:
        - Single Node Database: A single node database can handle low QPS with minimal complexity.
        - Simple Load Balancer: For application servers, a simple load balancer can distribute traffic across a few nodes
    - 100 - 1,000 QPS:
        - Database Replicas: Use read replicas to offload read traffic and improve read scalability.
        - Caching Layer: Implement caching (e.g., Redis, Memcached) to reduce database load and improve response times for frequently accessed data.
    - > 1,000 QPS:
        - Sharding or Partitioning: Distribute data across multiple database shards to handle write-heavy loads.
        - Advanced Load Balancing: Use techniques like consistent hashing to distribute traffic evenly across a large number of nodes.

- Database types
    - SQL
    - NoSQL
    - Graph

- Storage capacity

2. Performance

- Latency
- Availability

### Design

#### Endpoint design

#### Techstack choise

#### Database Diagram

#### System High-level design

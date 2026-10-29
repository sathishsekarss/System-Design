# Table of contents

1. [The 5 Evaluation Dimensions of System design](#5-evauation-dimensions-of-system-design)
1. [The 5 step interiew execution plan](#5-step-interview-execution-plan)

## 5-evauation-dimensions-of-system-design
1. **Communication & Collaboration**
   - Asks clarifying questions upfront rather than making unvalidated assumptions.
   - Treats the interviewer as a peer and collaborator, regularly checking in to validate direction.

2. **Structured Thinking**
   - Follows a systematic framework instead of randomly jumping between different system components.

3. **Technical Judgment**
   - Justifies technology choices (e.g., SQL vs. NoSQL, caching strategies, and message queues) based on specific requirements rather than personal preferences.

4. **Practical Depth**
   - Demonstrates real-world production experience by identifying failure modes, edge cases, single points of failure, and scaling bottlenecks.

5. **Time Management**
   - Paces the conversation effectively across 45–60 minutes without getting bogged down in a single detail too early.

## 5-step-interview-execution-plan
#### Step 1: Clarify Requirements (5–10 Minutes)

- **Functional Requirements**
  - Define core use cases to focus on (e.g., user upload, play song).
  - Explicitly rule out out-of-scope features.

- **Non-Functional Requirements**
  - Identify constraints, including Daily/Monthly Active Users (DAU/MAU).
  - Determine read-to-write ratios.
  - Define latency expectations.
  - Establish availability and downtime tolerance.

- **Alignment Check**
  - Ask the interviewer if the defined scope looks solid before drawing any components.

#### Step 2: Data & API Layer (15–20 Minutes)

- **Data Modeling**
  - Identify primary entities and relationships (1:N, N:M).
  - Define primary and foreign keys.
  - Estimate data sizes per record.
  - Establish where strong consistency is required versus where eventual consistency is acceptable.

- **API Design**
  - Define REST/gRPC endpoints.
  - Specify request and response formats.
  - Address pagination.
  - Define rate-limiting strategies.
  - Establish error-handling mechanisms.

- **Database Selection**
  - Choose appropriate storage solutions (e.g., PostgreSQL, MongoDB, S3).
  - Explain the trade-offs of the alternatives considered or omitted.

#### Step 3: High-Level Architecture (15–20 Minutes)

- **Core Components**
  - Load Balancers
  - Stateless API Servers
  - Primary & Replica Databases
  - Caching Layers (with TTL and invalidation strategies)
  - Message Queues (for decoupling)

- **User Journey Flow**
  - Walk the interviewer step-by-step through how read and write requests flow from the client application through gateway layers to the database and back.

- **CAP Theorem Trade-offs**
  - Address choices between Consistency, Availability, and Partition Tolerance for different components.

#### Step 4: Bottlenecks, Scale, & Reliability (5–10 Minutes)

- **Single Points of Failure (SPOFs)**
  - Identify fragile areas in the architecture.
  - Introduce redundancy (e.g., multi-AZ deployments, auto-scaling groups).

- **High-Load Bottlenecks**
  - Address performance under peak traffic.
  - Consider distributed caching.
  - Evaluate database sharding.
  - Implement connection pooling.

- **Observability**
  - Include health checks.
  - Monitor key metrics, including latency (p50/p95/p99) and error rates.
  - Establish automated alerting.

#### Step 5: Trade-offs & Future Extensions (Wrap-up)

- **Architectural Trade-offs**
  - Summarize the key architectural trade-offs made during the session.

- **Future Scalability**
  - Propose how the system could be extended if the load scaled significantly (e.g., 10x user growth).
  - Identify potential improvements if additional time were available.

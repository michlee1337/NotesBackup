- FOUNDATIONS
    - 0.0: Motivation
        - Demand
            - Internet companies handling scale of data
            - Businesses want short dev cycles and flexible models for market analysis
            - Users demand higher availability
        - Supply
            - Multi core processors and fast networks allow parallelism
            - IaaS (AWS) allow small teams to build distributed
        - Goals:
            - Frameworks of thought
            - How
            - Why
            - Further Questions
        - Relevance
            - Apps are data intensive (vs comp-intensive)
            - Need functionality:
                - Store data (databases)
                - Remember to speed up expensive reads (cache)
                - Search / filter in various ways (indexes)
                - Send messages
        - Thinking about Data Systems
            - Traditionally, db queue cache
                - Defined by how you access them, implement them, and their performance tradeoffs
            - New tools blur lines
                - Redis: datastore and message queue
                - Kafka: queues with database durability
            - Apps need unique combination of requirements
                - Developers need to stitch together tools in app code based on tasks
                - Ex: keeping cache or index consistent with db
                    - ![](https://lh5.googleusercontent.com/G8Wo4Dhl3PmXoIha6f4Kmh9yDiqChNJLJBIRjwjsQaBQDuLExvBLFKdLWV0c_RoD6NLVMYG-WDv1HC2Av7G5rhyJeGCwdm9NMPDG8WrxeCtMiUkOmMGoPr3CU_gZ31K3pblBA1P9)
                - App designers need to design data systems
            - Design questions
                - Accuracy, consistency, scaling, interface
                - Factors to consider
                    - Who’s involved
                    - Legacy dependencies
                    - Time scale
                    - Risk tolerance
    - 1.0: Overview
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Facsoc%2FLHgQK0_8Fz.png?alt=media&token=051be234-beaf-420d-8025-e97088ee744c)
        - Reliability
            - Overall
                - Working correctly when things go wrong
                    - performs as expected
                    - tolerates user/ software mistakes
                    - performance is good enough under load and volume
                    - enforces authorisation system and prevents abuse
                    - i.e. fault-tolerant/ resilient
                        - *always to a certain extent/ type because 100% is impossible
                        - *fault = one component of system deviates from spec (failure is when the whole sys doesn't provide service)
                    - good to stress test (Netflix Chaos Monkey)
                    - 
                - Important for safety and producivity
                    - responsibility to users
                    - tradeoff w dev/ ops cost, be conscious
            - Hardware
                - Ex: Hard Disk MTTF = 10-50 years, 1 death/day
                - Solutions
                    - add hardware redundancy
                    - software tolerance techniques
            - Software
                - more unpredictable and larger effects than hardware
                - most dangerous: some assumption of environment becomes false
                - preventive measures
                    - thinking through assymptions and interactions
                    - testing
                    - isolating processes
                    - stress testing
                    - monitor, analyse production (automated even better)
            - Human
                - design to minimise possibility of error
                    - abstractions, apis, admin interfaces
                        - *can't be too restrictive either, since people will hack it
                    - decouple mistake prone places (provide sandbox envs)
                    - (automated) testing at all levels
                    - make recovery easy 
                        - rollback
                        - small rolls
                        - tools for re-computation
            - Importance
        - Scalability
            - Load
                - best choice of params depends on system
                - 
            - Performance
                - with the same system resources (CPU, memory, network bandwidth), how is performance affected?
                - if you increase load parameter, how much do you need to increase resources?
                - metrics
                    - throughput
                    - response time - what the client sees.- service time
                        - network + queue delays
                    - latency = request wait for handling (awaiting service)
                - more metrics
                    - median and tail latency (worst case)
                    - Service Level Objectives/ Agreements
                - head of line. blocking
                    - queue delays
            - Load Management
        - Maintainability
            - Operability Making operations easy
            - Simplicity
            - Evolvability
        - 
    - 2.0: Data Models and Query Languages
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Facsoc%2Ffq9Lsel7BH.png?alt=media&token=c7eb38c4-4753-487e-aab6-18cdd11a4e51)
        - Relational vs Document
            - Object-Relational Mismatch (?)
            - Many to One and Many to Many
            - Document Database history
            - Relational vs today document
        - Query Languages
            - Declarative Queries in Web
            - MapReduce Querying
        - Graph Like Data Models
            - Property Graphs
            - Cypher Query L
            - Graph Queries SQL
            - Triple Stores and SPARQL
            - Datalog (foundation)
        - Summary
    - 3.0: [[Storage and Retrieval]]
    - 4.0: [[Encoding and Evolution]]
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Facsoc%2FLGkP0dgtc7.png?alt=media&token=c8001f8f-17ea-40a8-ba8e-727989bd517a)
        - Formats for Encoding
            - Lang Specific
            - JSON, XML, Binary
            - Thrift and Protocol
            - Avro
            - Merits of Schemas
        - Models of Dataflow
            - Through Database
            - Through Services: REST and RPC
            - Message Passing
- DISTRIBUTION
    - Why distribute
        - Reliable: availability and latency
            - multiple machines provide redundancy
            - geographic spread of servers makes UX faster
        - Scale: spread the load across machines
    - 5: [[Replication]]
    - 6: [[Partitioning]]
    - 7: [[Transactions]]
    - 8: [[problems]]
    - 9: [[Consistency and Consensus]]
- DERIVED DATA
    - 10: [[Batch Processing]]
    - 11: [[Stream Processing]]
    - 12: [[Future]]

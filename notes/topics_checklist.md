# Topics Checklist: Professional Data Engineer in Python

Check items off as I can explain them **without notes**, or demonstrate them from scratch.
DataCamp completion does not count. Section numbers follow the folder numbers; see the
README "Track items" table for the current platform order.

**Status 2026-09-29:** DataCamp shows Course 1 and Testing (section 8) complete, and the
Data Engineer Associate cert was earned. Nothing below is checked yet because nothing has
been demonstrated from a blank file.

---

## 1. Understanding Modern Data Architecture

- [ ] Draw a modern data architecture end to end: ingestion, storage, processing, serving
- [ ] Explain the transversal components: governance, orchestration, security, observability
- [ ] Explain data lake vs data warehouse vs lakehouse
- [ ] Explain ELT vs ETL and when each applies
- [ ] Explain the medallion (bronze/silver/gold) pattern

## 2. Introduction to Shell

- [ ] Navigate and manipulate files and directories confidently
- [ ] Use `grep`, `cut`, `sort`, `uniq`, `head`, `tail`, `wc`
- [ ] Combine tools with pipes and redirection
- [ ] Write a loop for batch processing
- [ ] Write and run a shell script with variables and arguments
- [ ] Use environment variables and understand PATH

## 3. Containerization and Virtualization Concepts

- [ ] Explain the difference between a VM and a container
- [ ] Explain what a container image is and how layers work
- [ ] Explain why containers matter for reproducibility
- [ ] Explain where Kubernetes fits relative to Docker

## 4. Introduction to dbt

- [ ] Explain what dbt does and what problem it solves
- [ ] Set up a dbt project structure
- [ ] Write a dbt model and understand `ref()`
- [ ] Explain materializations (view, table, incremental)
- [ ] Write a dbt test
- [ ] Explain the analytics engineering workflow

## 5. Object-Oriented Programming in Python

- [ ] Write a class with `__init__`, instance attributes, and methods
- [ ] Explain class attributes vs instance attributes
- [ ] Use inheritance and explain when it is appropriate
- [ ] Explain polymorphism with a concrete example
- [ ] Use `@property`, `@classmethod`, `@staticmethod` correctly
- [ ] Implement `__repr__`, `__eq__`, and other dunder methods
- [ ] Refactor one of my own notebooks into a proper class-based module

## 6. NoSQL Concepts

- [ ] Explain when NoSQL beats relational and when it does not
- [ ] Explain column-oriented storage and why it suits analytics (Snowflake)
- [ ] Explain document databases and query Postgres JSON
- [ ] Explain key-value stores and a Redis use case
- [ ] Explain graph databases and a use case
- [ ] Explain CAP theorem in plain language

## 7. Introduction to DevOps

- [ ] Explain what DevOps is beyond the buzzword
- [ ] Describe a CI/CD pipeline stage by stage
- [ ] Explain DevOps architecture components
- [ ] Explain how DevOps practices apply specifically to data pipelines
- [ ] Explain infrastructure as code at a high level
- [ ] Have a rehearsed answer to "what CI/CD tools do you use?"

## 8. Unit Testing in Python  **(highest interview priority)**

- [ ] Write a test with **pytest** from scratch
- [ ] Use `assert` effectively and read a pytest failure report
- [ ] Write and use **pytest fixtures**
- [ ] Parametrize a test
- [ ] Test for expected exceptions
- [ ] Explain unit vs integration vs end-to-end tests
- [ ] Write tests with **unittest** and explain the difference from pytest
- [ ] Explain mocking and write one mocked test
- [ ] Explain test coverage and its limits
- [ ] Have a rehearsed answer to "how would you test this?"

## 9. Introduction to PySpark

- [ ] Explain what Apache Spark is and the problem it solves
- [ ] Explain the driver/executor model
- [ ] Create and manipulate a Spark DataFrame
- [ ] Explain lazy evaluation and actions vs transformations
- [ ] Write a PySpark SQL query
- [ ] Explain when Spark is overkill vs necessary

## 10. Big Data Fundamentals with PySpark

- [ ] Explain the 3 Vs and what "big data" actually means operationally
- [ ] Explain RDDs and when they are still used
- [ ] Perform RDD transformations and actions
- [ ] Use Spark SQL and DataFrames over RDDs
- [ ] Explain partitioning and shuffling
- [ ] Explain a common Spark performance problem and its fix

## 11. Streaming Concepts

- [ ] Explain batch vs streaming and the tradeoffs
- [ ] Explain micro-batch processing
- [ ] Describe the components of a streaming system
- [ ] Explain windowing
- [ ] Explain exactly-once vs at-least-once delivery
- [ ] Give two real use cases where streaming is genuinely required

## 12. Apache Kafka

- [ ] Explain the Kafka architecture: broker, topic, partition, offset
- [ ] Explain producers and consumers and consumer groups
- [ ] Explain replication and fault tolerance
- [ ] Explain why Kafka is a log, not a queue
- [ ] Describe a data pipeline that uses Kafka end to end

## 13. Introduction to Kubernetes

- [ ] Explain pods, deployments, and services
- [ ] Explain what the scheduler and control plane do
- [ ] Deploy a simple application on K8s
- [ ] Explain scaling and self-healing
- [ ] Explain how K8s is used for data engineering and MLOps workloads

## Bonus: Introduction to Docker

- [ ] Run and manage Docker containers
- [ ] Write a Dockerfile from scratch
- [ ] Build and tag an image
- [ ] Explain layer caching and how to optimize a Dockerfile
- [ ] Explain Docker security practices (non-root user, minimal base images)
- [ ] Containerize one of my own projects

## Bonus: Data Processing in Shell

- [ ] Download data files from the command line (`curl`, `wget`)
- [ ] Chain shell tools with Python scripts in a pipeline
- [ ] Schedule a job with `cron`

---

## Projects

- [ ] **Debugging Sales Data** — completed and written up
- [ ] **Cleaning E-commerce Data with PySpark** — completed and written up

---

## Cross-cutting outcomes

- [ ] Every course has a `notes.md` written in my own words
- [ ] `notes/interview_answers.md` holds rehearsed answers for testing, CI/CD, Docker,
      Spark, and Kafka questions
- [ ] At least one personal project is containerized, tested, and CI-wired end to end
- [ ] I can walk someone through my dev-to-prod path without hedging

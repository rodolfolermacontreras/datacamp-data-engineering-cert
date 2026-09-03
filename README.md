# Professional Data Engineer in Python

**Provider:** DataCamp (Career Track)
**Level:** Advanced
**Format:** 13 courses, 2 projects, 3 bonus courses, ~40 hours
**Prerequisite:** Data Engineer in Python (completed)
**Participants:** 17,277
**Repo:** https://github.com/rodolfolermacontreras/datacamp-data-engineering-cert
**Started:** September 2026 | **Current completion:** 9%

**Instructors:** Mike Metzger (Data Engineer Consultant, Flexible Creations),
Cem Sakarya (Instructor and DevOps Risk Advisor), Miller Trujillo (Staff Software
Engineer, Connectly.ai)

---

## Why I am taking this

My analytics and modeling work is solid. The gap is everything **around** the model:
containerization, orchestration, testing, CI/CD, distributed processing, and streaming.
That gap has cost me in interviews, specifically on "how would you test this?" and
"what does your dev-to-prod path look like?"

This track is the systematic fix. It is not about becoming a data engineer. It is about
being a data scientist who can ship.

---

## Goals

1. Be able to describe and defend a **modern data architecture** end to end: ingestion,
   storage, processing, serving, governance, orchestration
2. Be fluent enough in **shell** to work comfortably on remote machines and in pipelines
3. Containerize my own work with **Docker** and understand where **Kubernetes** fits
4. Write **production-grade Python**: OOP structure, pytest, unittest, fixtures
5. Understand **dbt** and the analytics engineering workflow
6. Process data at scale with **PySpark** (RDDs, DataFrames, Spark SQL)
7. Understand **batch vs streaming** and be able to explain **Kafka**
8. Have working answers to DevOps and CI/CD interview questions, backed by real practice

---

## Track structure

### Core courses

| # | Course | Chapters | Folder |
|---|---|---|---|
| 1 | Understanding Modern Data Architecture | 4 | `01-understanding-modern-data-architecture/` |
| 2 | Introduction to Shell | 5 | `02-introduction-to-shell/` |
| 3 | Containerization and Virtualization Concepts | 2 | `03-containerization-virtualization-concepts/` |
| 4 | Introduction to dbt | 3 | `04-introduction-to-dbt/` |
| 5 | Object-Oriented Programming in Python | 3 | `05-object-oriented-programming-python/` |
| 6 | NoSQL Concepts | 4 | `06-nosql-concepts/` |
| 7 | Introduction to DevOps | 4 | `07-introduction-to-devops/` |
| 8 | Unit Testing in Python | 4 | `08-unit-testing-python/` |
| 9 | Introduction to PySpark | 3 | `09-introduction-to-pyspark/` |
| 10 | Big Data Fundamentals with PySpark | 3 | `10-big-data-fundamentals-pyspark/` |
| 11 | Streaming Concepts | 4 | `11-streaming-concepts/` |
| 12 | Apache Kafka | 2 | `12-apache-kafka/` |
| 13 | Introduction to Kubernetes | 3 | `13-introduction-to-kubernetes/` |

### Projects
`projects/`

| Project | Focus |
|---|---|
| Debugging Sales Data | Sharpen debugging skills to improve sales data accuracy |
| Cleaning E-commerce Data with PySpark | Distributed data cleaning at scale |

### Bonus material (0 of 3 complete)
| Course | Folder |
|---|---|
| Introduction to Docker | `bonus-introduction-to-docker/` |
| Data Processing in Shell | `bonus-data-processing-in-shell/` |
| (third bonus, confirm on platform) | |

---

## Course detail

### 1. Understanding Modern Data Architecture
Key components of modern data architecture, from ingestion and serving to governance and
orchestration.
- Introduction to Modern Data Architecture (750 XP)
- Modern Data Architecture Components (1050 XP)
- Transversal Components of Data Architectures (950 XP)
- Putting It All Together (800 XP)

### 2. Introduction to Shell
Manipulating files and directories, manipulating data, combining tools with pipes,
batch processing, creating new tools.

### 3. Containerization and Virtualization Concepts
Foundations of containerization and virtualization; applications of containerization.
Virtual machines, containers, Docker, Kubernetes at a conceptual level.

### 4. Introduction to dbt
Welcome to dbt, dbt projects and models, more on dbt models. The analytics engineering
workflow: version-controlled, tested, documented SQL transformations.

### 5. Object-Oriented Programming in Python
OOP fundamentals, inheritance and polymorphism, integrating with standard Python.
**Directly relevant:** this is the structural discipline that separates a notebook from
a shippable module.

### 6. NoSQL Concepts
Introduction to NoSQL databases, column-oriented databases (Snowflake), document
databases (Postgres JSON), key-value and graph databases (Redis).

### 7. Introduction to DevOps
Introduction to DevOps, DevOps architecture, implementation of DevOps for data
engineering, accurate and predictive and unbiased data with DevOps.

### 8. Unit Testing in Python
Creating tests with pytest, pytest fixtures, basic testing types, writing tests with
unittest. **Highest interview value in the track.** This closes a gap that has already
cost me once.

### 9. Introduction to PySpark
Introduction to Apache Spark and PySpark, PySpark in Python, introduction to PySpark SQL.

### 10. Big Data Fundamentals with PySpark
Big data concepts, RDDs, Spark SQL and DataFrames.

### 11. Streaming Concepts
Methods for processing data, intro to streaming, streaming systems, real-world use cases.
Batch vs streaming tradeoffs.

### 12. Apache Kafka
Kafka components, Kafka details. Topics, partitions, producers, consumers, brokers.

### 13. Introduction to Kubernetes
Introduction to Kubernetes, deploying software on K8s, data engineering and MLOps on K8s.

---

## Repo structure

```
datacamp-data-engineering/
├── README.md
├── 01-understanding-modern-data-architecture/
├── 02-introduction-to-shell/
├── ...
├── 13-introduction-to-kubernetes/
├── bonus-introduction-to-docker/
├── bonus-data-processing-in-shell/
├── projects/             # the 2 track projects
└── notes/                # cross-course notes, interview answers, cheat sheets
```

Each course folder should end up with:
- `notes.md` — what I actually learned, in my own words
- `code/` — exercise solutions and anything worth keeping
- Any reusable snippets promoted to `notes/`

---

## Progress

| # | Course | Status | Completion |
|---|---|---|---|
| 1 | Understanding Modern Data Architecture | In progress | 21% |
| 2 | Introduction to Shell | Not started | |
| 3 | Containerization and Virtualization Concepts | Not started | |
| 4 | Introduction to dbt | Not started | |
| 5 | Object-Oriented Programming in Python | Not started | |
| 6 | NoSQL Concepts | Not started | |
| 7 | Introduction to DevOps | Not started | |
| 8 | Unit Testing in Python | Not started | |
| 9 | Introduction to PySpark | Not started | |
| 10 | Big Data Fundamentals with PySpark | Not started | |
| 11 | Streaming Concepts | Not started | |
| 12 | Apache Kafka | Not started | |
| 13 | Introduction to Kubernetes | Not started | |
| P1 | Project: Debugging Sales Data | Not started | |
| P2 | Project: Cleaning E-commerce Data with PySpark | Not started | |

**Track completion: 9%**

---

## Priority order (if time is short)

Courses 8 (Unit Testing), 5 (OOP), and 7 (DevOps) have the highest immediate return.
They map directly to the "production-ready Python" gap documented in
`Coding_Practice/production_ready_python.md` and to questions I have already been asked
and answered poorly.

Courses 9, 10, 12, 13 build the distributed and infrastructure vocabulary. Those matter
for credibility in system design conversations.

---

## Notes to self

- Do not just click through. For each course, write the `notes.md` in my own words.
  If I cannot explain it without the slides, I did not learn it.
- Anything from this track that shows up in an interview question goes into
  `notes/interview_answers.md` as a rehearsed answer.
- Connect this back to `Coding_Practice/practice_plan.md`. The Saturday project track is
  where this material gets applied instead of just consumed.

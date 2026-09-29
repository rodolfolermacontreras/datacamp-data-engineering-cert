# Professional Data Engineer in Python

**Provider:** DataCamp (Career Track)
**Level:** Advanced
**Format:** 13 courses, 5 chapters, 2 projects, 3 bonus items, ~40 hours
**Prerequisite:** Data Engineer in Python (completed)
**Participants:** 17,727
**Repo:** https://github.com/rodolfolermacontreras/datacamp-data-engineering-cert
**Started:** September 2026 | **Current completion:** 15% (as of 2026-09-29)

**Certification earned:** DataCamp **Data Engineer Associate**, 2026-09-29
(credential `DEA0016275089433`). See [Certifications](#certifications).

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

DataCamp restructured the track. The list below matches the platform as of 2026-09-29.
Folder names were kept from the original layout, so the Folder column maps each item to
where its notes and code live.

### Track items (platform order)

| # | Type | Item | Folder |
|---|---|---|---|
| 1 | Course | Understanding Modern Data Architecture | `01-understanding-modern-data-architecture/` |
| 2 | Course | Introduction to Shell | `02-introduction-to-shell/` |
| 3 | Course | Containerization and Virtualization Concepts | `03-containerization-virtualization-concepts/` |
| 4 | Course | Introduction to dbt | `04-introduction-to-dbt/` |
| 5 | Course | Introduction to Object-Oriented Programming in Python | `05-object-oriented-programming-python/` |
| 6 | Course | Introduction to NoSQL | `06-nosql-concepts/` |
| 7 | Course | DevOps Concepts | `07-introduction-to-devops/` |
| 8 | Course | Introduction to Testing in Python | `08-unit-testing-python/` |
| 9 | Course | Introduction to Docker (moved from bonus to core) | `bonus-introduction-to-docker/` |
| 10 | Course | Introduction to PySpark | `09-introduction-to-pyspark/` |
| 11 | Chapter | Introduction to Big Data analysis with Spark | `10-big-data-fundamentals-pyspark/` |
| 12 | Chapter | Programming in PySpark RDDs | `10-big-data-fundamentals-pyspark/` |
| 13 | Chapter | PySpark SQL and DataFrames | `10-big-data-fundamentals-pyspark/` |
| 14 | Chapter | Downloading Data on the Command Line | `bonus-data-processing-in-shell/` |
| 15 | Chapter | Data Pipeline on the Command Line | `bonus-data-processing-in-shell/` |
| 16 | Course | Streaming Concepts | `11-streaming-concepts/` |
| 17 | Course | Introduction to Apache Kafka | `12-apache-kafka/` |
| 18 | Course | Introduction to Kubernetes | `13-introduction-to-kubernetes/` |

### Bonus material (0 of 3 complete)
`projects/` holds the two projects.

| Type | Item | Focus |
|---|---|---|
| Project | Debugging Code | Debug a sales data pipeline to fix accuracy issues |
| Project | Cleaning an Orders Dataset with PySpark | Distributed data cleaning at scale |
| Webinar | Impactful Data Engineering, with Datadog's Wouter de Bie | Industry context |

---

## Course detail

Numbering in this section follows the folder numbers, not the current platform order.
See [Track items](#track-items-platform-order) for the mapping.

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

Two columns on purpose. **DataCamp** is what the platform says. **Demonstrated** is the
real bar: done from a blank file and explained without hedging.

| # | Item | DataCamp | Demonstrated |
|---|---|---|---|
| 1 | Understanding Modern Data Architecture | Complete | No (no `notes.md` yet) |
| 2 | Introduction to Shell | 0% | No |
| 3 | Containerization and Virtualization Concepts | 0% | No |
| 4 | Introduction to dbt | 0% | No |
| 5 | Introduction to OOP in Python | 3% | No |
| 6 | Introduction to NoSQL | 0% | No |
| 7 | DevOps Concepts | 0% | No |
| 8 | Introduction to Testing in Python | Complete | **No (priority gap)** |
| 9 | Introduction to Docker | 0% | No |
| 10 | Introduction to PySpark | 81% | No |
| 11-13 | PySpark chapters (Big Data, RDDs, SQL and DataFrames) | 0% | No |
| 14-15 | Command line chapters (downloading data, pipelines) | 0% | No |
| 16 | Streaming Concepts | 0% | No |
| 17 | Introduction to Apache Kafka | 0% | No |
| 18 | Introduction to Kubernetes | 3% | No |
| B1 | Project: Debugging Code | Not started | No |
| B2 | Project: Cleaning an Orders Dataset with PySpark | Not started | No |
| B3 | Webinar: Impactful Data Engineering (Datadog) | Not started | n/a |

**Track completion (DataCamp): 15%**

---

## Certifications

| Certification | Date | Credential | Notes |
|---|---|---|---|
| DataCamp Data Engineer Associate | 2026-09-29 | `DEA0016275089433` | Timed exam + practical exam |

Timed exam scores: Data Management Theory 199, Data Management in PostgreSQL 182
(weakest), Exploratory Analysis Theory 200. Average 193, required 110.

- Recap of every question: [notes/exam_recap_data_management.md](notes/exam_recap_data_management.md)
- One-page study sheet: [notes/exam_cheatsheet_data_management.html](notes/exam_cheatsheet_data_management.html)
- Verify: https://www.datacamp.com/certificate/DEA0016275089433

**Honest caveat:** the timed exam answers were worked through with help. The cert is
real, but the PostgreSQL items flagged in the recap still need to be re-drilled from memory.

---

## Next steps

1. **Testing (item 8): prove it.** DataCamp shows it complete, but it has not been
   demonstrated. Next session starts with a cold quiz and a blank-file pytest problem on my
   own code. Write `08-unit-testing-python/notes.md` and the "how would you test this?"
   answer in `notes/interview_answers.md`.
2. **OOP (item 5)**, then **DevOps Concepts (item 7)**.
3. **Finish Introduction to PySpark (item 10)**: 81%, close it out.
4. Backfill `notes.md` for Course 1 in my own words.
5. Re-drill the PostgreSQL weak spots from the exam recap.

---

## Priority order (if time is short)

Items 8 (Testing), 5 (OOP), and 7 (DevOps) have the highest immediate return.
They map directly to the "production-ready Python" gap documented in
`Coding_Practice/production_ready_python.md` and to questions I have already been asked
and answered poorly.

Items 9 to 18 (Docker, PySpark, streaming, Kafka, Kubernetes) build the distributed and
infrastructure vocabulary. Those matter for credibility in system design conversations.

---

## Notes to self

- Do not just click through. For each course, write the `notes.md` in my own words.
  If I cannot explain it without the slides, I did not learn it.
- Anything from this track that shows up in an interview question goes into
  `notes/interview_answers.md` as a rehearsed answer.
- Connect this back to `Coding_Practice/practice_plan.md`. The Saturday project track is
  where this material gets applied instead of just consumed.

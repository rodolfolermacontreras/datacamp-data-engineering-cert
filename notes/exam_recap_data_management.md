# Exam Recap: Data Management and Exploratory Analysis

**Date:** 2026-09-29
**Result:** PASSED (average 193, required 110)

| Topic | Score | % to target |
|---|---|---|
| Data Management Theory | 199 | 177% |
| Data Management in PostgreSQL | 182 | 145% |
| Exploratory Analysis Theory | 200 | 210% |

**Honest read:** passed, but not perfect. PostgreSQL was the weakest area. The questions
most likely to have cost points are flagged with **[RISK]** below. Those are the ones to
re-drill from a blank file.

**Caveat:** these answers were produced with help during the exam, not from memory. Passing
does not mean these topics are learned. The bar is still: write it from a blank file and
explain it without hedging.

---

## Part 1: Data Management Theory

### Q1. GCP service for real-time data from wearables and medical devices
**Options:** Compute Engine, Cloud Storage, Pub/Sub, Cloud SQL
**Reasoning:** "Real-time from multiple sources" is an ingestion problem. Compute Engine is
raw VMs, Cloud Storage is data at rest, Cloud SQL is a relational serving database. Pub/Sub
is managed messaging: producers publish, consumers subscribe, it scales and buffers bursts.
**Answer: Google Cloud Pub/Sub**
**Pattern:** Devices -> Pub/Sub (ingest) -> Dataflow (process) -> BigQuery / Cloud Storage.

### Q2. GCP service for authoring, scheduling, and monitoring workflows
**Options:** Dataflow, Composer, Pub/Sub, Dataprep
**Reasoning:** Author + schedule + monitor = orchestration. Composer is managed Apache
Airflow (DAGs in Python, retries, UI). Dataflow executes processing, Pub/Sub moves
messages, Dataprep is visual data cleaning.
**Answer: Google Cloud Composer**

### Q3. Key consideration when moving from logical to physical data model
**Options:** Normalization, mapping entity relationships, validating business logic,
optimizing database performance
**Reasoning:** Conceptual = what the business needs. Logical = entities, attributes,
relationships, normalized, engine-agnostic. Physical = how it is built on a real engine:
data types, indexes, partitioning, sometimes denormalization for speed. The other options
belong to earlier stages.
**Answer: Optimizing database performance**

### Q4. Distribute data across multiple physical servers
**Options:** Clustering, Sharding, Normalization, Denormalization
**Reasoning:** Sharding splits rows by a shard key and places each shard on a different
server. Clustering orders data on disk (or copies data for availability). Normalization and
denormalization are design choices, not distribution strategies.
**Answer: Sharding**
**Remember:** partitioning = split within one DB; sharding = split across servers;
replication = copies across servers.

### Q5. A set of one or more attributes that uniquely identify records
**Options:** Composite key, Foreign key, Index key, Super key
**Reasoning:** Textbook definition (Silberschatz, *Database System Concepts*): "A superkey
is a set of one or more attributes that, taken collectively, allow us to identify uniquely a
tuple." Composite requires two or more. Foreign key references another table. Index key is
for performance.
**Answer: Super key**
**Hierarchy:** super key (any unique set) -> candidate key (minimal super key) -> primary
key (the chosen candidate). Composite = any key with 2+ columns.

### Q6. GCP storage for large structured sales data used for analysis
**Options:** Dataflow, BigQuery, Google Drive, Cloud Storage
**Reasoning:** Structured + large + analytical = data warehouse. Dataflow processes but does
not store. Drive is consumer file sharing. Cloud Storage is object storage for raw or
unstructured files, not SQL-queryable natively.
**Answer: Google BigQuery**

### Q7. AWS service for real-time data processing
**Options:** Data Pipeline, Glue, EMR, Kinesis
**Reasoning:** Data Pipeline is legacy batch orchestration. Glue is serverless batch ETL.
EMR is managed Hadoop/Spark, mostly batch. Kinesis is managed real-time streaming.
**Answer: Amazon Kinesis**

---

## Part 2: Data Management in PostgreSQL

### Q8. psql command to see data types of columns in table `cars`
**Options:** `SELECT SCHEMA cars`, `SHOW TYPES cars`, `\d cars`, `\schema cars`
**Reasoning:** Backslash commands are psql meta-commands. `\d` = describe. The others are
invalid (`SHOW` only reads config settings).
**Answer: `\d cars`**
**SQL equivalent:** `SELECT column_name, data_type FROM information_schema.columns WHERE table_name = 'cars';`

### Q9. Usernames that end in a digit: `WHERE username ~ '[0-9]___'`
**Reasoning:** `~` is regex match. `[0-9]` alone matches a digit anywhere. `$` anchors to
end of string.
**Answer: `$`** -> `'[0-9]$'`

### Q10. Convert `amount` to INTEGER with rounding
**Reasoning:** Syntax is `ALTER COLUMN col TYPE new_type USING expression`.
**Answer: `TYPE INTEGER USING`**
```sql
ALTER TABLE sales ALTER COLUMN amount TYPE INTEGER USING ROUND(amount);
```

### Q11. Promo codes that start with 1-3 and end with 5-9
**Reasoning:** `^[1-3]` start, `.*` anything in between, `[5-9]$` end. Without `.*` it only
matches 2-character strings.
**Answer: `'^[1-3].*[5-9]$'`**

### Q12. Rows where `review_date` >= latest `end_date` for the same project
**Reasoning:** Correlated subquery (`WHERE project_id = ep.project_id`). "Latest" = MAX.
**Answer: `MAX(end_date)`**
**Window alternative:** `MAX(end_date) OVER (PARTITION BY project_id)`.

### Q13. Return data type of `hire_date`
**Answer: `pg_typeof`** -> `SELECT pg_typeof(hire_date) AS date_dtype FROM employees LIMIT 1;`

### Q14. Day of week from a date (output 3, 3, 1, 3, 3) **[RISK]**
**Reasoning:** `EXTRACT(field FROM date)`. `DOW` = 0-6, Sunday = 0. `ISODOW` = 1-7,
Monday = 1. Sample could not distinguish them. `DOW` is the standard answer.
**Answer: `DOW`**

### Q15. Return data type of `salary` with alias "Data Type"
**Answer: `pg_typeof`**
**Note:** double quotes = identifiers (column/alias names), single quotes = string values.

### Q16. Add NOT NULL constraint to `employee_id`
**Options:** `IS NOT NULL`, `SET NOT NULL`, `CHECK NOT NULL`, `NOT NULL`
**Reasoning:** Inside `ALTER COLUMN`, PostgreSQL requires `SET NOT NULL` / `DROP NOT NULL`.
`IS NOT NULL` is a WHERE predicate. Bare `NOT NULL` is only valid at column creation.
**Answer: `SET NOT NULL`**

### Q17. Exclude customers matching `'^CDX[0-9]+'` **[RISK]**
**Options:** `NOT SIMILAR TO`, `NOT IN`, `NOT LIKE`, `<>`
**Reasoning:** Only `SIMILAR TO` supports `[0-9]` and `+`. `LIKE` only understands `%` and
`_`. `NOT IN` and `<>` compare literal values.
**Answer: `NOT SIMILAR TO`**
**Caveat:** `SIMILAR TO` must match the whole string and `^` is not a real anchor there.
In real PostgreSQL, use `customer !~ '^CDX[0-9]+$'`.

### Q18. Convert text reading (e.g. '878.6') to integer
**Reasoning:** Text -> NUMERIC first (arbitrary precision), then `::INTEGER` (rounds).
Casting `'878.6'::INTEGER` directly errors.
**Answer: `CAST`, `NUMERIC`** -> `CAST(reading AS NUMERIC)::INTEGER`

### Q19. Convert Eastern timestamps to Pacific
**Answer: `AT TIME ZONE`** -> `time_est AT TIME ZONE 'America/Los_Angeles'`
**Trap:** on `timestamptz` it returns local `timestamp`; on `timestamp` it returns
`timestamptz`. Use named zones, not fixed offsets, for DST.

### Q20. Exclude membership levels starting with P or p
**Answer: `WHERE level !~`** -> `WHERE level !~ '^[Pp]'` (or `!~* '^p'`)
**Operators:** `~` match, `!~` not match, `~*` / `!~*` case-insensitive.

### Q21. Recode preferences other than Active/Beach to 'Other'
**Answer: `'Other'`, `NOT IN`**
```sql
UPDATE holiday_clients SET preference = 'Other'
WHERE preference NOT IN ('Active', 'Beach');
```
**NULL trap:** `NULL NOT IN (...)` is NULL, not TRUE. Add `OR preference IS NULL`.

### Q22. Bakery spend per transaction (join CTE to transactions)
**Answer: `a.item_id = b.item_id`**
**Note:** must qualify with aliases or it is ambiguous. INNER JOIN filters out non-Bakery.

### Q23. Books that have at least one sale
**Answer: `EXISTS`** -> `WHERE EXISTS (SELECT * FROM sales WHERE book_id = b.book_id)`
**Why not JOIN:** a JOIN duplicates the book once per sale. `NOT EXISTS` is NULL-safe
unlike `NOT IN`.

### Q24. Planes whose average flight time > 200 minutes
**Answer: `WHERE airplane_id IN` and `HAVING AVG(minutes) > 200`**
**Rule:** `WHERE` filters rows before grouping (no aggregates). `HAVING` filters groups
after grouping (aggregates allowed).

### Q25. Banned usernames and reason **[RISK]**
**Answer: `b.reason`, `INNER JOIN`, `ON a.user_id = b.user_id`**
**Note:** schema image did not load during the exam. Q26 later confirmed the key was
`user_id`. If a different key was entered, this may have lost points.

### Q26. All data from both tables for banned users, join on `(user_id)`
**Answer: `USING`** -> `FROM accounts JOIN banned USING (user_id)`
**ON vs USING:** `USING` requires the same column name in both tables and outputs it once.

### Q27. Bakery spend as a proportion of total spend
**Answer: `bakery_spend`** (the CTE with `transaction_id` and `bakery_spend`)
**Why:** LEFT JOIN keeps transactions with no Bakery items (NULL). `MAX(b.bakery_spend)`
recovers a value that repeats once per item row. `* 1.00` forces decimal division.

### Q28. Combine AMER, EMEA, APAC visits and sum globally
**Answer: `UNION ALL` (both blanks)**
**Why not UNION:** UNION removes duplicate rows. Identical rows from two regions would
collapse and undercount the total. UNION ALL is also faster.

---

## Part 3: Exploratory Analysis Theory

### Q29. Temperature vs ice cream sales
**Answer: scatterplot** (two numeric variables, relationship)

### Q30. Advertising spend vs sales revenue
**Answer: Scatter plot**
**Interview angle:** correlation is not causation. Causal claims need an experiment
(A/B, geo holdout) or causal methods.

### Q31. Distribution of feedback scores for each experience level, single chart
**Answer: Box plot** (distribution per category, side by side)

### Q32. Distribution of exam scores for a class
**Answer: histogram**

### Q33. New subscribers per $100k increase in ad spend
**Answer: A scatterplot** (with fitted regression line; slope x $100k answers the question)

### Q34. A heat map is most useful...
**Answer: To see how a value changes depending on two other features.**
Hierarchical data = treemap. Normality = histogram / Q-Q plot.

### Q35. Relative frequency of continuous values
**Answer: histogram** (`density=True` or `stat="probability"` for relative frequency)

### Q36. School budget by category across several years
**Answer: Line chart** (time on x-axis, one line per category)

### Q37. Aggregation of numeric values across two categorical dimensions
**Answer: Pivot table**

### Q38. Distribution of test scores to judge difficulty
**Answer: Histogram**
**Why not box plot:** single group; histogram shows shape and skew. Right-skewed = hard.

### Q39. How to read IQR from a boxplot
**Answer: Based on the width of the box from one end to the other** (Q3 - Q1)
**Outlier rule:** below Q1 - 1.5 x IQR or above Q3 + 1.5 x IQR.

### Q40. Average salary by job title, grouped by department
**Answer: pivot table**

### Q41. Light blue band around a seaborn regression line
**Answer: The confidence interval** (95%, bootstrapped, around the mean prediction)
**CI vs PI:** CI = uncertainty of the line (narrow). PI = uncertainty of a single new point
(wide, includes irreducible noise).

### Q42. Main reason to use a pivot table over a spreadsheet
**Answer: view the sales summaries in different ways**

---

## Where points were likely lost (re-drill these)

| Area | Why it is weak | Drill |
|---|---|---|
| Regex operators and `SIMILAR TO` | Mixed up which syntax supports which metacharacters | Write 5 filters from blank: `~`, `!~`, `~*`, `LIKE`, `SIMILAR TO` |
| Date extraction fields | `DOW` vs `ISODOW` vs `DAY` vs `DOY` | Run `EXTRACT` on a Sunday date with each field |
| JOIN keys when schema is not visible | Guessed the key | Always read the schema first; `USING` hints at shared names |
| Time zones | `timestamp` vs `timestamptz` behavior flips | Run `AT TIME ZONE` on both types and compare |
| NULL behavior | `NOT IN` with NULLs | Write a query that proves the trap, then fix with `NOT EXISTS` |

**Cheat sheet:** [exam_cheatsheet_data_management.html](exam_cheatsheet_data_management.html)

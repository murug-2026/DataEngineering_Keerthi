###### Data: The Fundamentals
**1. What is Data - Simply?**
Data is recorded observations about the world: facts, measurements, or descriptions captured in a form you can store and analyze. A single data point means little on its own. "98.6" is just a number until you know it's a body temperature in °F or °C  for patient #14 on a given morning. Data = values + context.

**2. What are the different types of data (numeric, categorical, text, time-series, etc.)?**
|Type	|What it is|	Example|
|----|----|----|
|**Numeric, continuous**|Any value in a range, can have decimals|Weight, blood glucose, temperature
|**Numeric, discrete**	|Countable whole numbers	|Number of hospital visits, survey responses|
|**Categorical, nominal**|	Labels with no order|	Blood group, city, gender|
|**Categorical, ordinal**|	Labels with a meaningful order|	Pain scale (mild/moderate/severe), education level
|**Text**|	Free-form language	|Doctor's notes, survey comments, reviews|
|**Time-series**|	Values recorded in time order, where the order itself matters|	Daily heart rate, monthly sales|
|**Others**	|Images, audio, geospatial, graph/network|	X-rays, ECG signals, GPS coordinates|

Why the distinction matters: the type decides which operations make sense. You can average heights, but not blood groups. You can rank pain levels, but the "distance" between mild and moderate isn't measurable.

**3. What is the difference between qualitative and quantitative data?**
**Quantitative data** is numerical and answers "how much / how many" (age, income, cholesterol level).
**Qualitative data** is descriptive and answers "what kind / why / how" (opinions, interview answers, "I skip breakfast because of early classes").

The two overlap. Qualitative data can be coded into quantitative form, for example turning "satisfied / neutral / dissatisfied" into 3/2/1, or counting how often a theme appears in interviews. Quantitative data tells you what is happening, and qualitative data often explains why.

**4. What is the difference between raw data and processed data?**

**Raw data** is data as first collected: untouched, messy, possibly with typos, blanks, duplicates, and inconsistent formats ("M", "male", "Male").
**Processed data** has been cleaned, standardized, transformed, or aggregated so it can be analyzed (missing values handled, units unified, variables derived, records summarized).

Think of it as ingredients versus a prepared meal. Always keep a copy of the raw data, so your processing steps are reproducible and you can fix mistakes later.

**5. Why data is the foundation of data science**

Everything in data science, whether statistics, visualization, or machine learning, is a method for extracting patterns from data. Models don't "know" anything beyond what the data shows them. So:

A brilliant algorithm on poor data gives poor results ("garbage in, garbage out").
Data defines what questions you can answer. If you never recorded a patient's age, no model will discover its effect.
In practice, a large share of a data scientist's time goes to finding, cleaning, and understanding data, not to modelling.
**6. What makes data good or bad**
|Quality dimension|	Question it asks|	Bad-data example|
|---|---|---|
|**Accuracy**	|Does it reflect reality?|	A blood pressure typed as 1200 instead of 120|
|**Completeness**|	Is everything needed present?|	30% of patients missing an age|
|**Consistency**|	Is it uniform across records and sources?|	"Chennai" vs "Madras" vs "chennai"|
|**Timeliness**|	Is it recent enough for the purpose?|	Using 2015 prescribing data for a 2026 decision|

##### Information - Turn Data into meaning

**1. What is information, and how is it different from data?**
Data is raw, unprocessed facts: 38.9, Patient 14, 12 Nov. Information is data that has been organized and interpreted so it answers a question or supports a decision.
|   |Data	|Information|
|---|---|---|
|**Nature**|Raw facts, symbols, values|	Processed, meaningful, interpreted|
|**Meaning on its own**|	Little or none	|Has meaning and purpose|
|**Example**|	38.9, 39.2, 38.7|	"Patient 14 has had a fever above 38.5 °C for three consecutive days"|
|**Usefulness**|Needs work before use|	Ready to inform a decision|

The same item can be both, depending on the stage. The output of one analysis (a monthly average) can become the data input for the next (comparing averages across years). The usual ladder is **Data → Information → Knowledge → Decision/Action.**

**2. How does data become information?**

Through processing steps that add structure and meaning:

1. **Collect**: gather the raw values.
Clean: fix errors, remove duplicates, handle missing values.
2. **Organize**: sort, group, and label (by patient, by month, by branch).
3. **Summarize or analyze**: compute totals, averages, trends, comparisons.
4. **Interpret and present**: state what it means, usually via a table, chart, or a plain statement.

**Example:** a list of 200 canteen purchase records is data. "Tea and samosa account for 40% of evening sales, and sales drop sharply after 6 pm" is information.

**3. What is context, and why is it important for converting data into information?**

Context is the surrounding detail that tells you what the data refers to and how to read it. It includes:

- What was measured and in what units
- Who or what it applies to
- When and where it was recorded
- How it was collected
- Compared to what (a benchmark, a baseline, a previous period)

Without context, data is ambiguous or misleading. "120" could be blood pressure, a price in rupees, or a page count. Even with units, you need a comparison point: a fasting glucose of 110 mg/dL means something different from a post-meal reading of 110 mg/dL. Context is what converts a number into a meaningful statement

**4. What are examples where the same data produces different information depending on context?**

- **The number 102:** a body temperature in °F means fever. As a bus route, it's a destination. As an exam score out of 200, it's about 51%.
- **Heart rate of 150 bpm:** during a sprint, normal. While resting in bed, a possible emergency. In a newborn, close to normal.
- **Sales fell 10% in December:** for a fireworks shop, alarming. For a business whose busy season is October to November, expected. After a price hike, perhaps even a good result.
- **A hospital's 5% readmission rate:** good or bad depends on the type of hospital, patient age mix, and what comparable hospitals achieve.
- **A survey result of "70% prefer canteen food":** if the 70% comes from 15 hostel students, it says something very different than from 500 students across all campuses.

**5. Why do businesses rely on information rather than raw data?**

- Raw data can't be acted on. Millions of transaction rows don't tell a manager what to stock. A summary of top-selling products by week does.
- Decisions need a conclusion, not a pile of facts. Information is already filtered toward a question.
- It saves time and reduces error. Decision-makers can't read raw records, and eyeballing raw data leads to wrong impressions.
- It reveals patterns and trends that individual values hide, such as seasonality, customer segments, and unusual behavior.
- It enables comparison and accountability: against targets, competitors, or last year.
- It supports prediction and planning, since forecasts are built on trends, not on isolated numbers.

##### Databases - Where Data Lives

**Database Fundamentals**

**1. What Is a Database, and Why Do We Need One?**

A database is an organized collection of data stored so it can be retrieved, updated, and managed efficiently.

You need one because once data grows beyond a handful of records, or several people and programs need it at once, loose files stop working.

A database provides:
- Fast searching and retrieval.
- Shared access.
- Data consistency.
- Data safety through backups and permissions.

**2. Problems with Excel Instead of a Database**

- **Redundancy:** A customer's address gets retyped in every order row, so one change means many edits.
- **Inconsistency:** "Chennai", "chennai", and "Madras" can all coexist, and nothing stops it.
- **Concurrency:** Many users editing at once can lead to overwritten work or file locks.
- **Scale and Speed:** Performance and usability can decline as datasets grow.
- **Weak Integrity:** Nothing inherently prevents an order for a customer who doesn't exist.
- **Limited Security:** You cannot easily control "this user may read but not edit this column."
- **Poor Relationships:** Joining data across sheets means fragile lookups instead of real relationships.
- **No Recovery or Audit Trail:** Recovering from errors and tracking changes can be difficult without additional systems.

**Note:** Excel is still useful for small, single-user analysis.

**3. What Is a DBMS?**

A **Database Management System (DBMS)** is software that creates, stores, and manages databases.

It handles:
- Queries.
- Security.
- Concurrent access.
- Transactions.
- Backups.
- Data integrity rules.

**Examples:**
- MySQL
- PostgreSQL
- Oracle Database
- Microsoft SQL Server
- MongoDB
- Redis

**4. Database vs. DBMS**

The **database** is the data itself. The **DBMS** is the software that manages it.

**Real-world analogy:**

The database is like the books in a library, while the DBMS is like the librarian and cataloguing system that helps you find and borrow them.

The same DBMS can manage multiple databases.

**5. Main Types of Databases**

| Type | Data Structure | Best For | Examples |
|---|---|---|---|
| **Relational (SQL)** | Tables with fixed columns, linked by keys | Structured data, transactions, reporting | PostgreSQL, MySQL |
| **Document** | JSON-like documents, each can differ | Flexible, nested records (profiles, catalogs) | MongoDB |
| **Key-Value** | Simple key → value pairs | Caching, sessions, fast lookups | Redis, DynamoDB |
| **Columnar** | Data stored by column rather than row | Analytics over huge datasets | Cassandra, ClickHouse |
| **Graph** | Nodes and edges representing relationships | Social networks, recommendations, fraud detection | Neo4j |

**6. Table, Row, Column, Primary Key, and Foreign Key**

Consider the following two tables.

**Patients**

| patient_id (PK) | name | city |
|---|---|---|
| 1 | Asha | Chennai |
| 2 | Ravi | Coimbatore |

**Visits**

| visit_id (PK) | patient_id (FK) | date |
|---|---|---|
| 101 | 1 | 2026-03-02 |
| 102 | 1 | 2026-04-10 |


- **Table:** A collection of related data about one kind of entity (Patients).
- **Row (Record or Tuple):** One entry in the table (Asha's details).
- **Column (Field or Attribute):** One property shared by all rows (city).
- **Primary Key (PK):** A column whose value uniquely identifies each row. It must be unique and never NULL.
- **Foreign Key (FK):** A column that refers to another table's primary key. `Visits.patient_id` links each visit to a patient, and the database can refuse a visit for a patient who doesn't exist.

**7. What Is a Schema?**

A schema is the blueprint of the database.

It defines:
- Tables.
- Columns.
- Data types.
- Keys.
- Constraints.
- Relationships.

**Example:**

The Patients table has:
- `patient_id` as an integer primary key.
- `name` as text that cannot be NULL.

**Key Takeaway:** A schema defines the structure of a database, not the data itself.

**8. Why Do Relational Databases Enforce Structure?**

Relational databases enforce structure because predictability provides important guarantees.

- **Data Integrity:** Types and constraints reject invalid data (text in a date column, missing required values).
- **Consistency Across Relationships:** Foreign keys prevent orphaned records.
- **Powerful Queries:** Since every row has the same structure, SQL can join, filter, and aggregate data reliably.
- **Reliable Transactions (ACID):** For example, a bank transfer either fully happens or doesn't happen at all.

**Trade-off:** Changing the structure later takes planning, such as performing schema migrations.

**9. Why Do NoSQL Databases Allow Flexibility?**

- **Evolving or Varied Data:** One product has 3 attributes and another has 30. Documents can differ without redesigning a schema.
- **Faster Development:** You can store data in the shape your application already uses.
- **Horizontal Scaling:** Many NoSQL systems are designed to distribute data across multiple servers to handle huge volumes of data or traffic.
- **Specialized Models:** Graph, key-value, and columnar databases are each optimized for particular access patterns.

**Trade-off:** The application, rather than the database, may become responsible for much of the consistency checking, and complex cross-record queries are often harder.

**Structured vs. Unstructured Data**

**What is structured data?**
Structured data is organized in a fixed, predefined schema of rows and columns, where every record has the same fields and data types. It is easy to store, search, and query.

**Examples:** customer tables, bank transactions, inventory records, spreadsheets, patient lab results.

| PatientID | Age | Glucose (mg/dL) | Visit Date |
|-----------|-----|-----------------|------------|
| 101       | 45  | 110             | 2026-03-02 |
| 102       | 52  | 145             | 2026-03-05 |

**What is unstructured data?**
Unstructured data has no predefined format or schema. It doesn't fit neatly into rows and columns, and its meaning has to be extracted through processing.

**Examples:** emails, PDFs, images, X-rays, audio, video, social media posts, doctors' free-text notes.

It makes up roughly 80% or more of all data generated today.

**What is semi-structured data (JSON, XML)?**
Semi-structured data has no rigid table schema but contains tags, keys, or markers that give it internal organization and hierarchy. It sits between the two extremes.

**JSON example:**
```json
{
  "patient_id": 101,
  "name": "A. Kumar",
  "diagnoses": ["diabetes", "hypertension"],
  "visits": [
    {"date": "2026-03-02", "glucose": 110}
  ]
}
```

**XML example:**
```xml
<patient id="101">
  <name>A. Kumar</name>
  <diagnosis>diabetes</diagnosis>
</patient>
```

Fields can vary between records (one record may have extra keys), and data can be nested. Other examples include log files, HL7/FHIR health records, and API responses.

**Why do companies generate more unstructured data today?**
- **Social media and web content:** posts, reviews, comments, and videos are created constantly.
- **Smartphones and cameras:** photos, voice notes, and video are easy to capture.
- **IoT and sensors:** continuous streams of machine and device readings.
- **Digital communication:** emails, chats, meeting recordings, and support tickets.
- **Digitized documents:** scanned records, contracts, and PDFs.
- **Cheap storage:** cloud storage makes keeping everything affordable.
- **Rich media in healthcare:** medical imaging, ECG waveforms, and clinical notes.

**What tools handle structured data well (SQL databases)?**
Relational databases (RDBMS) and data warehouses are built for fixed schemas:
- **MySQL, PostgreSQL, Oracle, Microsoft SQL Server, SQLite**
- **Data warehouses:** Snowflake, Amazon Redshift, Google BigQuery
- **Analysis tools:** Excel, Tableau, Power BI

**Why they work well:** SQL enables fast queries, joins, aggregations, ACID transactions (reliability), and enforced data integrity.

**What tools handle unstructured data well (NoSQL, Hadoop, cloud storage)?**

| Category | Tools | Best for |
|----------|-------|----------|
| **NoSQL databases** | MongoDB, Cassandra, Redis, Neo4j | Flexible schemas, documents, graphs, key-value data |
| **Big data frameworks** | Hadoop (HDFS, MapReduce), Apache Spark | Distributed processing of huge datasets |
| **Cloud object storage** | Amazon S3, Azure Blob Storage, Google Cloud Storage | Cheap, scalable storage of files, images, and video |
| **Search engines** | Elasticsearch, Solr | Full-text search over documents and logs |
| **Data lakes** | AWS Lake Formation, Databricks | Holding raw data in any format |
| **AI/ML tools** | NLP libraries, computer vision models, LLMs | Extracting meaning from text, images, and audio |

**Why is unstructured data harder to analyze?**
- **No schema:** you can't simply query it with SQL.
- **Needs preprocessing:** text must be cleaned and tokenized, images processed, and audio transcribed.
- **Ambiguity:** language involves slang, sarcasm, and context; images vary in quality and angle.
- **Large volume and variety:** it takes lots of storage and computing power.
- **Inconsistent quality:** data can be noisy, incomplete, or duplicated.
- **Hard to label:** supervised ML needs manual annotation, which is costly.
- **Privacy concerns:** documents and images often contain sensitive information that is hard to detect and anonymize.

**How does structured data help in machine learning?**
- **Ready-to-use features:** columns map directly to input variables (features) and target labels.
- **Consistent format:** less cleaning and fewer conversion steps are required.
- **Easier feature engineering:** you can compute statistics, ratios, and encodings easily.
- **Works with classical algorithms:** regression, decision trees, random forests, and XGBoost perform very well on tabular data.
- **Better data quality control:** validation rules reduce errors and missing values.
- **Faster training and easier interpretation:** results are simpler to explain, which matters in fields like healthcare and finance.
- **Simple evaluation:** clear labels make accuracy, precision, and recall easy to measure.


**1. How would you convert unstructured data (text, logs, images) into structured form?**

The general idea is to extract meaningful fields from raw content and place them into a schema (rows and columns).

Text (emails, reviews, clinical notes)
- Cleaning: lowercase, remove noise, fix encoding.
- Tokenization and normalization: split into words, apply stemming or lemmatization.
- Named Entity Recognition (NER): pull out names, dates, drugs, diseases, locations.
- Classification and sentiment analysis: assign labels such as positive/negative or topic.
- Embeddings or TF-IDF: convert text into numeric vectors.

**For example:**
|Raw Text|Structured Output|
|---|---|
|Patient reports chest pain since 2 days, started aspirin| `Symptom = Chest Pain`, `Duration = 2 days`, `Drug = Aspirin`|

**Logs**
Parsing with regex or tools: Logstash, Fluentd, Python `re`.
Split into fields: timestamp, log level, source, message.

**For example:**

**Raw Data**

``2026-03-02 10:15:32 ERROR payment-service Timeout after 30s``

**Output**

|Timestamp|Level|Service|Message|
|---|---|---|---|
|2026-03-02 10:15:32|ERROR|Payment-service|Timeout after 30s|


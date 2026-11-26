**Data Lifecycle and Business Data Flow**

**1. What is the data lifecycle (creation → storage → usage → archival → deletion)?**

*Creation* - Data is generated or captured: a customer placed an order, a patient is registered, a sensor logs a temperature. Quality is largely decided here.

*Storage* - Data is persisted in databases, data warehouses, data lakes, or files. Access control, backup, and cost

*Usage* - Data is processed, queried, analyzed, and turned into reports, dashboards, models, and decisions. This is where value is realized.

*Archival* - Data that is no longer needed daily is moved to cheaper, slower storage but retained for compliance, audit, or occasional analysis

*Deletion* - Data is securely destroyed when retention periods end or when a person requests erasure. Reduces storage costs and breach exposure.

**2. Why is understanding the lifecycle important in data science and business intelligence?**

- Data Quality
- Trust and Reproducability
- Governance and Compliance
- Cost and performance
- Right data at the right time - Analysts waste most of their time on data that is stale, duplicated, or poorly documented.

**3. Main data sources in business**

| Source | Examples | Typical nature |
|---|---|---|
| **Databases** | MySQL, PostgreSQL, Oracle behind an app | Structured, transactional |
| **Spreadsheets** | Excel and Google Sheets used by teams | Semi-structured, manually maintained, error-prone |
| **APIs** | Payment gateways, social media, weather, third-party services | Structured (JSON/XML), pulled on demand or pushed |
| **Sensors / IoT** | Wearables, lab instruments, factory machines, GPS | High-volume, time-stamped streams |
| **Logs** | Web server logs, app logs, clickstreams, audit trails | Semi-structured text, very high volume |
| **Others** | Surveys, emails, PDFs, images, scanned documents | Unstructured |

**4. How data flows from source systems to reporting systems**

Source systems → Ingestion → Staging area → Transformation (cleaning, joining, standardizing) → Data warehouse → Semantic or BI layer → Dashboards, reports, ML models

**5. Operational vs. analytical data**

|  | **Operational (OLTP)** | **Analytical (OLAP)** |
|---|---|---|
| **Purpose** | Run day-to-day transactions | Support analysis and decisions |
| **Operations** | Many small inserts, updates, deletes | Large reads, aggregations, scans |
| **Data scope** | Current, detailed | Historical, often summarized |
| **Design** | Normalized (reduce redundancy) | Denormalized / dimensional (fast queries) |
| **Users** | Clerks, apps, customers | Analysts, managers, data scientists |
| **Example** | "Record this patient's lab result" | "Average lab turnaround time by month across all hospitals" |

**6. How do businesses use data in applications like CRM, ERP, HR, finance, healthcare?**

CRM (Customer Relation Management) : Customer Profiles, Interaction, and Sales Pipeline. Used for segmentation, churn prediction, lead scoring, and campaign analysis.

ERP (enterprise resource planning): Inventory, procurement, manufacturing, and supply chain. Used for demand forecasting, stock optimization, and cost analysis.

HR: Employee records, attendance, payroll, recruitment. Used for attrition analysis, workforce planning, and performance trends.

Finance: Ledgers, invoices, budgets. Used for reporting, fraud detection, forecasting, and audit.

Healthcare: Electronic Health Records, Bed Occupancy and wait times  in hospitals for admission, Public Health Information, lab and imaging System.  

**7. What are common challenges in data flow (duplication, latency, inconsistency)?**

- Missing or Incorrect data
- Schema Changes 
- Security and Privacy
- Silo - Separate  Data should not be joined

**8. How does ETL (Extract, Transform, Load) fit into the data lifecycle?**

**Extract:** Pull data from sources (databases, files, APIs, logs) without disrupting them.
**Transform:** Clean, validate, deduplicate, standardize, enrich, aggregate, and apply business rules.
**Load:** Write the result into the warehouse or analytical store, either as a full reload or incrementally.







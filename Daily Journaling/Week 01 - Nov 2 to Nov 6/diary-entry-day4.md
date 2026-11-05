
# Data Lifecycle and Data Flow

## 1. What is the data lifecycle (creation → storage → usage → archival → deletion)?

The data lifecycle refers to the different stages data goes through from creation to deletion.
1. **Creation:** Data is generated or collected through forms, applications or transactions.
2. **Storage:** Data is saved in databases, spreadsheets or cloud storage.
3. **Usage:** Data is processed, analysed and used for decision-making.
4. **Archival and Deletion:** Old data is stored for future reference and eventually deleted securely when no longer required.

## 2. Why is understanding the lifecycle important in data science and business intelligence?

Understanding the data lifecycle ensures that data is properly managed at every stage.
1. It helps maintain data quality and consistency.
2. It ensures sensitive information is stored and used securely.
3. It helps data scientists access reliable data for analysis.
4. It supports better business decisions through accurate reports.
5. It reduces storage costs and ensures compliance with data regulations.

## 3. What are the main data sources in business (databases, spreadsheets, APIs, sensors, logs)?

Businesses collect data from different sources to monitor operations and make informed decisions.
1. **Databases:** Store customer details, orders and transactions (e.g., MySQL).
2. **Spreadsheets:** Organise and analyse data (e.g., Microsoft Excel).
3. **APIs:** Allow applications to exchange data with other systems.
4. **Sensors:** Collect real-time information from physical devices.
5. **Logs:** Record system activities, user actions and errors.

## 4. How does data flow from source systems to reporting systems?

Data flows from source systems to reporting systems through collection, transformation and storage.
1. **Source Systems:** Generate data through databases, applications and APIs.
2. **Extraction:** Collects data from different sources using ETL tools.
3. **Transformation:** Cleans, validates and converts data into a consistent format.
4. **Storage:** Processed data is stored in a data warehouse.
5. **Reporting:** Tools like Power BI and Tableau present data through dashboards and reports.

## 5. What is the difference between operational data and analytical data?

Operational data supports daily business activities, whereas analytical data supports business analysis and decision-making.

| Operational Data | Analytical Data |
|---|---|
| Supports daily business operations. | Supports business analysis. |
| Contains current, detailed information. | Often contains historical and summarised information. |
| Updated frequently in real time. | Updated periodically or through data pipelines. |
| Used for transaction processing. | Used for reporting and forecasting. |
| Example: Customer placing an Amazon order. | Example: Analysing monthly Amazon sales trends. |

## 6. How do businesses use data in applications like CRM, ERP, HR, finance, healthcare?

Businesses use data in different applications to manage operations, improve efficiency and make better decisions.
1. **CRM:** Stores customer details, purchase history and interactions.
2. **ERP:** Manages inventory, sales, production and supply chains.
3. **HR:** Manages employee records, attendance, payroll and recruitment.
4. **Finance:** Tracks revenue, expenses, budgets and profitability.
5. **Healthcare:** Manages patient records, medical history and treatment information.

## 7. What are common challenges in data flow (duplication, latency, inconsistency)?

Data flow challenges can affect data accuracy, consistency and availability across systems.
1. **Duplication:** The same data is stored multiple times, creating repeated records.
2. **Latency:** Delays in data transfer result in outdated information.
3. **Inconsistency:** Different systems store the same data in different formats or values.
4. **Data Loss:** Information may be lost during transfer due to technical failures.
5. **Integration Issues:** Incompatible systems make data exchange difficult.

## 8. How does ETL (Extract, Transform, Load) fit into the data lifecycle?

ETL is a data integration process that collects, cleans and transfers data into a destination system for analysis.
1. **Extract:** Collects data from databases, spreadsheets, APIs and applications.
2. **Transform:** Cleans, filters, validates and converts data into a consistent format.
3. **Load:** Transfers processed data into a data warehouse or database.
4. ETL connects data collection with data storage and usage.
5. It prepares reliable data for reporting, business intelligence and data science.

**Example:** Amazon extracts sales data, transforms it into a standard format and loads it into a data warehouse to analyse sales performance.

**Business Requirements & Data Documentation**

**1. What are business requirements in the context of data projects?**

Business requirements describe what the organization needs to achieve and the questions it needs data to answer, without specifying how the data work will be done. They come from stakeholders such as managers, analysts, and clinicians

Example:

Question:

Reduce the patient readmission by 10% this year
- Which departments have the highest readmission rates?
- *Users:* Who will use the output and for what decision.
- *Success Criteria:* How the business will know the project worked
- *Criteria:* Deadlines, Budget, Compliance rules(eg.,Patient Privacy)

**2. Why translate business needs into data requirements?**

Stakeholders speak in business terms      while data teams need precise, testable specifications.

**Removes ambiguity -** "Active customer" must become something like "a customer with at least one transaction in the last 90 days."

**Prevents rework -** Building the wrong dataset or dashboard is expensive to fix later.

**Aligns expectations -** Business and technical teams agree on scope, definitions, and deliverables.

**Makes the work testable -** Clear requirements allow validation against agreed criteria.

**Identifies the gaps early -** You discover whether the required data exists, is accessible, and is of sufficient quality.

**3. What is a data dictionary?**

A data dictionary is a centralized reference document that describes the data in a dataset or database. What each field means, how it is stored, and how it should be used.Think of it as a instruction manual for your data.

**4. What are the key elements of a data dictionary (field name, type, format, description)?**

| Element         | Purpose                                     | Example                                               |
| --------------- | ------------------------------------------- | ----------------------------------------------------- |
| **Field name**  | Unique identifier for the column            | `patient_dob`                                         |
| **Data type**   | How the data is stored                      | Date, Integer, Varchar(50), Boolean                   |
| **Format**      | Expected structure or pattern               | `DD-MM-YYYY`, 10-digit phone number                   |
| **Description** | Plain-language meaning and business context | Patient's date of birth as recorded at registration |

**5. How does documentation help data quality and team collaboration?**

**Data quality**
- Standard defintion means everyone calculates the metric same way
- Documented rules (formats, valid ranges) make validation and error detection easier.
- Data lineage records show where data came from and how it was transformed, which helps trace errors back to their source.
**Team Collaboration**
- New members onboard faster instead of reverse engineering the data
- Reduces dependence on one person's knowledge
- Reduces repeated questions and misinterpretations.
- Supports audits, compliance, and reproducibility

**6. What is the difference between technical documentation and business documentation?**

**Technical Documentation**

- Used by Developers, Data engineers, BI Developers
- Architecture, Implementation and logic

*Example*

ER Diagrams, Schema Definitions, SQL code comments, Application programming interface docs 

**Business Documentation**

- Used by Stakeholders, Analysts, Managers and users
- Represents Goals and Definition
- Plain and domain specific

*Example*

Business requirement documents (BRD), Business glossary, User guides and Report descriptions.

**7. Why do BI developers and data engineers need strong documentation skills?**

- **Maintainability:** Pipelines, queries, and dashboards outlive their creators. Documentation makes them fixable and extendable.
- **Trust in data:** Users trust reports more when definitions and logic are transparent.
- **Faster debugging:** Documented transformations and dependencies shorten troubleshooting time.
- **Communication across roles:** They sit between business stakeholders and technical systems, so they must explain each side to the other.
- **Professional Value:** Clear documentation shows rigor and is often what distinguishes a strong engineer or analyst from an average one.




# 📗 Day 2 — Completeness & Missing Data

## Learning Objectives
By the end of this day, you should be able to:
- Understand completeness as a data quality dimension
- Identify different types of missing data (NULL, blank, zero, default values)
- Calculate completeness metrics for datasets
- Understand the business impact of missing data
- Design strategies to handle missing values

---

## 📚 Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What is Completeness?**
- **Definition**: Are all required data fields present in a record?
- **Question**: Does the record have values for all attributes needed for its purpose?
- **Examples**:
  - Customer record missing email address
  - Order missing delivery date
  - Employee record without salary information
  - Invoice without tax amount calculation

**Types of Missing Data**
- **NULL/Empty**: Explicitly missing in the database
- **Blank**: Space or empty string instead of actual value
- **Zero as default**: Zero entered instead of actual missing value (e.g., $0 revenue for active store)
- **Coded missing**: -1, 999, "NA", "Unknown" used to represent missing
- **Not Applicable**: Field not relevant for this record type

**Why Data Goes Missing**
- **Optional fields**: Fields user doesn't fill in form
- **Not yet collected**: Process incomplete (pending delivery date)
- **Data loss**: System error, failed integration, database corruption
- **Legacy systems**: Old data doesn't have all fields new system requires
- **Access restrictions**: Confidential data not provided (SSN partially masked)
- **Business reasons**: Some entities don't have certain attributes (subsidiary without parent company)

**Impact of Incomplete Data**
- **Analytics**: Can't analyze what's not there; skews results
- **Decisions**: Missing context leads to wrong conclusions
- **Operations**: Can't execute process without required information
- **Compliance**: Missing required documentation violates regulations
- **Relationships**: Can't link records if key identifiers missing

**Business Scenarios**
1. **E-commerce**: Missing shipping address prevents order fulfillment
2. **CRM**: Missing contact info prevents customer outreach
3. **HR**: Missing salary data affects payroll processing
4. **Medical**: Missing allergy info could harm patient
5. **Financial**: Missing transaction details prevents audit trail

**Completeness Metrics**
- **Field completion rate**: % of records with non-null value for field
  - Formula: `Count(Non-Null) / Total Records * 100`
- **Record completeness**: % of fields filled per record
- **Dataset completeness**: Average completeness across all records
- **Critical field completeness**: Must be 100% for certain fields

**Handling Missing Data Strategies**
- **Accept it**: For truly optional fields, missing is okay
- **Reject records**: If critical field missing, exclude from analysis
- **Fill with default**: Use placeholder (0, "Unknown") for analysis
- **Impute values**: Estimate missing based on similar records
- **Investigate root cause**: Why is it missing? Fix the source
- **Flag for manual review**: Mark records needing investigation

**Distinguishing Missing from Invalid**
- **Missing**: The field itself is absent
- **Invalid**: Field present but contains wrong value type
- Both are quality issues but handled differently

**Key Questions to Explore**
1. Which data fields are mandatory vs optional?
2. What's the business cost of each missing field?
3. How do you distinguish between "legitimately missing" and "should be present"?
4. How would you calculate completeness for your dataset?
5. When should you reject records vs fill missing data?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Identify Missing Data**
- Provided dataset: Customer records with various fields
- Tasks:
  - Identify all NULL, blank, and suspicious values
  - Count missing values per field
  - Categorize as "legitimately missing" vs "should be present"
  - Highlight critical fields vs optional fields

**Exercise 2: Calculate Completeness Metrics**
- Create completeness report showing:
  - For each field: count of missing values and % complete
  - Formula: `=COUNTA(NonBlankCells)/COUNTA(AllCells)*100`
  - For each record: % of fields populated
  - Overall dataset completeness score
- Identify fields with lowest completeness

**Exercise 3: Detect Missing Data Patterns**
- Use formulas to identify:
  - Records with missing critical fields: `=IF(OR(B2="", C2="", D2=""), "INCOMPLETE", "Complete")`
  - Fields with systematic patterns (e.g., always missing in certain regions)
  - Records with many fields missing vs one or two
- Create visualization showing missing data patterns

**Exercise 4: Design Missing Data Strategy**
- For sample dataset, decide for each field:
  - If missing is acceptable
  - If field is critical (must reject records)
  - If field can be imputed or filled
  - If root cause investigation needed
- Write business rule for each decision
- Test strategy on provided records

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain different types of missing data and why each occurs?
- [ ] How would you explain the business impact of incompleteness?
- [ ] Can you calculate completeness metrics for a dataset?
- [ ] When should you fill missing data vs reject records?

### Documentation Task
Write a brief explanation (300-400 words) covering:
- The difference between missing and invalid data
- Three business scenarios where incompleteness is a serious problem
- How you would measure and report completeness to stakeholders

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand completeness as a data quality dimension
- [ ] Know types of missing data (NULL, blank, zero, coded, N/A)
- [ ] Understand sources of missing data
- [ ] Know business impact of incompleteness
- [ ] Understand completeness metrics and calculation
- [ ] Know strategies for handling missing data

**Hands-On Practice**
- [ ] Identified missing data in sample dataset
- [ ] Distinguished legitimately missing from problematically missing
- [ ] Calculated field-level and record-level completeness metrics
- [ ] Detected patterns in missing data
- [ ] Created strategy for handling missing values
- [ ] Applied formulas to flag incomplete records

**Documentation**
- [ ] Documented completeness analysis
- [ ] Explained missing data handling strategy
- [ ] Reflected on business impact

---

## 📖 Reference Resources

- Missing data types and sources
- Completeness metric calculations
- Missing data imputation strategies
- Business impact analysis framework
- Excel formulas for detecting missing values

---

## 🎯 Next Steps

Tomorrow (Day 3) you'll learn about **Consistency** — ensuring data doesn't contradict itself, maintaining referential integrity, and identifying conflicting values.

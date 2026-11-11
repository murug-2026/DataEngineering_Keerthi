# 📘 Day 1 — Data Quality Fundamentals & Accuracy

## Learning Objectives
By the end of this day, you should be able to:
- Understand what data quality means in business context
- Define accuracy and why it matters for decision-making
- Identify accuracy issues in datasets
- Design accuracy validation rules
- Build automated accuracy checks in Excel

---

## 📚 Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What is Data Quality?**
- The degree to which data correctly represents the real-world entity or phenomenon
- Dimensions of data quality: accuracy, completeness, consistency, validity, timeliness, uniqueness
- Why organizations need data quality frameworks
- Business impact: Wrong decisions, compliance violations, customer churn, wasted resources

**The Accuracy Dimension**
- **Definition**: Does the data correctly represent the actual value in the real world?
- **Examples of inaccuracy**:
  - Customer age recorded as 250 years
  - Price negative when it should be positive
  - Sales region recorded incorrectly (NY instead of CA)
  - Invoice amount doesn't match line items
- **Why accuracy matters**:
  - Financial analysis: Inaccurate costs lead to wrong profit calculations
  - Customer service: Wrong customer data leads to service failures
  - Compliance: Financial regulations require accurate data
  - Analytics: Insights based on inaccurate data are misleading

**Sources of Inaccuracy**
- **Data entry errors**: Typos, manual mistakes, wrong data type entered
- **System errors**: Calculation mistakes, rounding errors in transfers
- **Measurement errors**: Sensors, equipment malfunction, calibration drift
- **Mapping/translation errors**: Incorrect code mapping, wrong conversion factors
- **Legacy data issues**: Outdated or obsolete reference data
- **Integration errors**: Data loss during ETL processes

**Types of Accuracy Problems**
- **Semantic accuracy**: Does the value mean what we think it means?
- **Numeric accuracy**: Are calculations and values correct?
- **Referential accuracy**: Do references point to correct entities?
- **Temporal accuracy**: Is the data current/valid at the right time?

**Business Scenarios**
1. **Retail Company**: Price data must be accurate. A $50 item priced at $5 costs money; priced at $500 loses sales.
2. **Healthcare**: Patient drug allergies must be accurate. Wrong data could cause harm.
3. **Financial Services**: Account balances must be accurate. Errors trigger regulatory fines.
4. **Supply Chain**: Inventory counts must be accurate. Errors lead to stockouts or overstock.
5. **Manufacturing**: Quality measurements must be accurate. Errors cause product defects.

**Accuracy Validation Strategies**
- **Range checks**: Is the value within expected bounds? (Age 0-120, Price > 0)
- **Comparison checks**: Does this value match a known reference? (Department code in allowed list)
- **Calculation checks**: Do derived values equal inputs? (Total = Sum of line items)
- **Cross-reference checks**: Does it match data in another table?
- **Duplicate checks**: Are there multiple records for the same entity with different values?

**Key Questions to Explore**
1. How would you know if customer age data is inaccurate?
2. What business decisions depend on accurate data?
3. How would you design a rule to catch inaccurate prices?
4. What's the difference between invalid data and inaccurate data?
5. Who should define what "accurate" means for each field?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Identify Inaccuracy Issues**
- Provided dataset: Sales transactions with customer info
- Tasks:
  - Review order amounts, customer ages, dates, prices
  - Identify values that seem suspicious or inaccurate
  - Document what makes them inaccurate
  - Categorize by type (semantic, numeric, referential, temporal)

**Exercise 2: Define Accuracy Rules**
- Create validation rules for:
  - Customer age (range check: 18-100)
  - Unit price (must be > 0)
  - Order date (must not be in future)
  - Quantity (must be integer > 0)
  - Revenue = Unit Price × Quantity
- Write each rule as a business requirement

**Exercise 3: Build Accuracy Checks in Excel**
- Create a validation column that checks:
  - `=IF(AND(Age>=18, Age<=100), "Valid Age", "INACCURATE: Out of range")`
  - `=IF(UnitPrice>0, "Valid Price", "INACCURATE: Negative or zero")`
  - `=IF(Revenue = UnitPrice*Quantity, "Valid Total", "INACCURATE: Math error")`
- Apply to provided dataset
- Count how many records fail each check

**Exercise 4: Compare Against Reference Data**
- Use lookup table with valid customer accounts
- Create formula: `=IF(COUNTIF(ValidCustomers, CustomerID)>0, "Valid", "NOT FOUND")`
- Identify customers that don't exist in master list
- Document findings

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain the difference between accuracy and completeness?
- [ ] What would happen to a business if customer price data was 10% inaccurate?
- [ ] How would you explain accuracy requirements to a business stakeholder?
- [ ] Can you design validation rules for a specific business scenario?

### Documentation Task
Write a brief explanation (300-400 words) covering:
- What makes data "accurate" vs "inaccurate" in business context
- Three specific business scenarios where accuracy is critical
- How you would validate accuracy for one of those scenarios

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand what data quality means and its business impact
- [ ] Understand accuracy as one dimension of data quality
- [ ] Know common sources of inaccuracy (entry errors, system errors, measurement, mapping, legacy, integration)
- [ ] Recognize different types of accuracy problems (semantic, numeric, referential, temporal)
- [ ] Understand accuracy validation strategies (range, comparison, calculation, cross-reference, duplicate)
- [ ] Identify accuracy issues in provided datasets

**Hands-On Practice**
- [ ] Identified inaccuracy issues in sample dataset
- [ ] Defined accuracy rules for business scenario
- [ ] Built accuracy validation formulas in Excel
- [ ] Applied checks to data and counted failures
- [ ] Compared data against reference/master data
- [ ] Documented which records failed validation

**Documentation**
- [ ] Explained accuracy in business context
- [ ] Documented validation rules clearly
- [ ] Reflected on business impact of inaccuracy

---

## 📖 Reference Resources

- Data quality frameworks and dimensions
- Accuracy validation techniques and examples
- Business impact of data accuracy
- Excel validation formula examples
- Reference data management best practices

---

## 🎯 Next Steps

Tomorrow (Day 2) you'll learn about **Completeness** — ensuring all required data is present and identifying missing values, gaps, and why they matter for analysis.

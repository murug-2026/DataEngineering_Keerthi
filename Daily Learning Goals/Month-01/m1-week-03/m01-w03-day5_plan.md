# 📒 Day 5 — Data Cleansing Methodology & Documentation

## Learning Objectives
By the end of this day, you should be able to:
- Understand complete data cleansing workflow
- Apply systematic methodology to real messy datasets
- Document cleansing steps for reproducibility
- Validate cleaned data against quality standards
- Create professional data quality reports

---

## 📚 Conceptual Understanding (3 hours)

### What is Data Cleansing?

**Definition**: The process of identifying and correcting (or removing) errors, inconsistencies, and quality issues in datasets.

**Why Data Cleansing Matters**
- "Garbage in, garbage out" principle
- Bad data leads to wrong analysis
- Data quality directly impacts business decision quality
- 20% of time: Acquiring data; 80% of time: Cleaning data
- Cleansed data is prerequisite for analytics and BI

**The ROI of Data Cleansing**
- Better decisions from reliable data
- Faster analysis (not fighting data issues)
- Reduced rework and error correction
- Improved customer data quality
- Regulatory compliance

### Common Data Quality Issues

**Missing Values**
- Blank cells in critical fields
- NULL values in database exports
- Incomplete records
- Example: Customer with no phone number

**Duplicates**
- Exact duplicates (identical records)
- Partial duplicates (same customer, different formats)
- Multiple entries for same entity
- Example: Same customer record entered twice

**Inconsistent Formats**
- Dates: "2024-11-11" vs "11/11/2024" vs "11-11-24"
- Phone: "1234567890" vs "(123) 456-7890" vs "123-456-7890"
- Names: "JOHN DOE" vs "John Doe" vs "john doe"
- Example: Region "East" vs "EAST" vs "east"

**Incorrect Data Types**
- Numbers stored as text
- Dates stored as text
- Text that should be numbers
- Example: Customer ID "00123" becomes 123

**Wrong Spellings & Typos**
- Misspelled product names
- Typos in addresses
- Incorrect codes
- Example: "Califonia" instead of "California"

**Extra Spaces & Special Characters**
- Leading/trailing spaces: "  Customer  "
- Multiple spaces: "John    Doe"
- Special characters: "O'Reilly" vs "Oreilly"
- Non-breaking spaces

**Incorrect Codes & References**
- Invalid product codes
- Non-existent customer IDs
- Codes from old systems not updated
- Example: Product code doesn't match master table

### The Data Cleansing Workflow

**Phase 1: Profiling**
- Understand the data
- Identify data types
- Find patterns and distributions
- Spot obvious issues
- Questions: How many records? How many duplicates? How many blanks?

**Phase 2: Issue Identification**
- Systematic scan for each type of issue
- Quantify issues (how many affected records?)
- Categorize severity
- Document findings
- Questions: What issues exist? How many? How severe?

**Phase 3: Defining Cleaning Rules**
- For each issue, define the solution
- Document the rule clearly
- Test rule on sample data
- Ensure rule is reversible (keep original copy)
- Example: "Remove leading/trailing spaces, then apply PROPER case"

**Phase 4: Applying Cleaning**
- Apply rules systematically
- Document each step applied
- Keep audit trail of changes
- Verify formulas/rules work correctly
- Questions: Which rows were affected? How many?

**Phase 5: Validation**
- Check cleaned data against quality standards
- Verify no data was lost unintentionally
- Spot check results
- Compare before/after samples
- Questions: Does cleaned data meet standards? Any issues introduced?

**Phase 6: Documentation**
- Document entire process
- Explain each cleaning rule
- Record counts (before/after)
- Note any exceptions or manual interventions
- Create audit trail

### The Data Dictionary

**Purpose**: Centralized reference for all data fields

**Includes**:
- Field name
- Field type (text, number, date, etc.)
- Format (length, pattern, expected values)
- Acceptable values
- Source (where does this come from?)
- Business meaning
- Quality standards
- Example values

**Benefits**:
- Ensures consistent understanding
- Guides data quality checks
- Supports new users
- Documents requirements

### The Data Quality Report

**Purpose**: Communicate data quality findings to stakeholders

**Includes**:
- Executive summary
- Data quality metrics
- Issues identified and severity
- Cleaning actions taken
- Results (before/after counts)
- Recommendations
- Audit trail

**Format**:
- Professional, clear language
- Visual summary (charts if helpful)
- Detailed appendix with specifics
- Easy for non-technical audience

### Best Practices for Data Cleansing

**Do's**
- ✓ Keep original data (never delete original before cleaning)
- ✓ Document every step
- ✓ Test on sample before applying to all data
- ✓ Keep audit trail
- ✓ Get stakeholder agreement on cleaning rules
- ✓ Validate results thoroughly

**Don'ts**
- ✗ Delete data without understanding impact
- ✗ Make assumptions about what data should be
- ✗ Skip validation
- ✗ Over-clean (fix only documented issues)
- ✗ Ignore edge cases

### Key Questions to Answer

1. What are the critical data quality issues for your industry?
2. How would you systematically clean a large messy dataset?
3. What would your data dictionary look like for your business?
4. How do you validate that cleaned data is correct?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercise: Complete Customer Database Cleaning

**Scenario**: You have a messy customer database exported from an old system with:
- Duplicate customer records
- Missing email addresses and phone numbers
- Inconsistent name formatting (mixed case)
- Phone numbers in different formats
- Addresses with typos and inconsistent formatting
- Extra spaces throughout
- Some records with invalid data

**Steps to Complete**:

**Step 1: Data Profiling (15 minutes)**
- Count total records
- Count blank/missing values per field
- Identify duplicate records
- Spot check sample records
- Document findings

**Step 2: Define Cleaning Rules (15 minutes)**
- Rule for duplicates: Keep first occurrence, remove rest
- Rule for names: TRIM + PROPER
- Rule for email: LOWER + TRIM
- Rule for phone: Standardize to (XXX) XXX-XXXX format
- Rule for addresses: TRIM + PROPER
- Rule for missing values: Mark as "Not Provided"
- Rule for data types: Convert text numbers to actual numbers

**Step 3: Apply Cleaning (30 minutes)**
- Create new sheet with cleaned data
- Apply TRIM to all text fields
- Apply PROPER to names/addresses
- Apply LOWER to email
- Format phone numbers using SUBSTITUTE
- Handle missing values with IFERROR
- Remove duplicate customer records
- Document each formula created

**Step 4: Validation (20 minutes)**
- Compare record counts: Original vs Cleaned
- Spot check 10 random records
- Verify no data was lost inappropriately
- Check for remaining quality issues
- Validate formatting is consistent

**Step 5: Documentation (20 minutes)**
- Create data quality report
- Document cleaning methodology
- Record before/after statistics
- Explain each cleaning rule
- Create data dictionary for cleaned data
- Prepare for stakeholder review

**Deliverables**:
- Cleaned customer dataset
- Data quality report (PDF or Word)
- Data dictionary
- Audit trail showing changes made

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain your cleansing methodology clearly?
- [ ] Can you produce a clean dataset from a messy one?
- [ ] Can you write professional data quality documentation?
- [ ] Can you identify when data quality is acceptable vs needs more work?

### Documentation Task
Prepare a 500-word document titled "Data Cleansing Methodology" that includes:
- Your systematic approach to identifying issues
- Specific rules you created and why
- How you validated the cleaned data
- How you documented the process
- Lessons learned

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand complete data cleansing workflow (6 phases)
- [ ] Identify common data quality issues
- [ ] Know difference between profiling and validation
- [ ] Understand what belongs in data dictionary
- [ ] Know what should be in data quality report
- [ ] Understand best practices and common mistakes

**Hands-On Practice**
- [ ] Profiled messy customer dataset
- [ ] Identified all data quality issues
- [ ] Defined specific cleaning rules
- [ ] Applied cleaning formulas systematically
- [ ] Validated cleaned data
- [ ] Removed duplicates
- [ ] Documented entire process

**Documentation**
- [ ] Created professional data quality report
- [ ] Created comprehensive data dictionary
- [ ] Documented audit trail of changes
- [ ] Prepared cleansing methodology explanation
- [ ] Reflected on challenges and solutions

---

## 📖 Reference Resources

- Data cleansing best practices frameworks
- Sample data quality reports
- Data dictionary templates
- Real-world case studies of data issues

---

## 🎯 Week 3 Summary

This week you've learned:
- **Day 1**: Logical functions (IF, IFS, AND, OR) for decision-making
- **Day 2**: Text extraction (LEFT, RIGHT, MID, LEN) for parsing data
- **Day 3**: Text cleaning (TRIM, UPPER, LOWER, PROPER, SUBSTITUTE)
- **Day 4**: Error handling (IFERROR) and date calculations
- **Day 5**: Complete data cleansing methodology and documentation

**Key Achievement**: You can now take a messy real-world dataset and transform it into clean, analysis-ready data while documenting every step.

**Next Week (Week 4)**: You'll learn lookup functions to combine multiple datasets together - the next layer of data integration and business analysis.
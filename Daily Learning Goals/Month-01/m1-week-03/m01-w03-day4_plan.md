# 📕 Day 4 — IFERROR, Date Functions & Conditional Formatting

## Learning Objectives
By the end of this day, you should be able to:
- Handle Excel errors gracefully using IFERROR
- Perform date calculations using date functions
- Apply conditional formatting for visual data quality insights
- Build reports with error-resilient formulas

---

## 📚 Conceptual Understanding (3 hours)

### Understanding Excel Errors

**Common Error Types**
- **#DIV/0!**: Division by zero (e.g., 10/0)
- **#VALUE!**: Wrong data type in formula (e.g., adding text to number)
- **#N/A**: Value not found in lookup formula (VLOOKUP, XLOOKUP)
- **#REF!**: Reference to deleted or invalid cell
- **#NAME?**: Excel doesn't recognize function name (typo)
- **#NULL!**: Problem with a range reference

**When Errors Occur in Reports**
- VLOOKUP fails when customer ID not found
- Date calculations fail with blank cells
- Division fails when denominator is zero
- Lookups fail when text has extra spaces

**Why Errors Matter**
- Errors in reports look unprofessional
- Errors cascade through dependent formulas
- Errors confuse users and distract from insights
- Reporting errors reduce data credibility

### The IFERROR Function

**Syntax**: `=IFERROR(value, value_if_error)`

**Purpose**: Test if formula produces error; if yes, return alternative value

**Example**:
```
=IFERROR(VLOOKUP(A1, $B$2:$C$100, 2, 0), "Not Found")
```
- If lookup succeeds: Return looked-up value
- If lookup fails: Return "Not Found"

**Benefits**
- Cleaner reports without error symbols
- User-friendly error messages
- Allows reporting to proceed even with missing data
- Makes formulas more robust

**Business Examples**
- Lookup customer name: "Not Found" if customer doesn't exist
- Calculate discount: 0% if customer not in discount table
- Retrieve price: "Contact Sales" if price not available
- Calculate ratio: 0 if denominator is zero

### Date Functions in Excel

**How Excel Stores Dates**
- Dates are stored as serial numbers
- January 1, 1900 = 1
- January 2, 1900 = 2
- Today = around 45,000+ depending on current date

**The TODAY Function**
- **Syntax**: `=TODAY()`
- **Purpose**: Returns today's date
- **Example**: TODAY() = 2024-11-11 (if run on Nov 11, 2024)
- **Updates automatically** each day

**The NOW Function**
- **Syntax**: `=NOW()`
- **Purpose**: Returns current date and time
- **Example**: NOW() = 2024-11-11 14:30:45
- **Updates automatically** when spreadsheet recalculates

**The YEAR Function**
- **Syntax**: `=YEAR(date)`
- **Purpose**: Extract year from date
- **Example**: YEAR(DATE(2024,3,15)) = 2024

**The MONTH Function**
- **Syntax**: `=MONTH(date)`
- **Purpose**: Extract month (1-12) from date
- **Example**: MONTH(DATE(2024,3,15)) = 3

**The DAY Function**
- **Syntax**: `=DAY(date)`
- **Purpose**: Extract day (1-31) from date
- **Example**: DAY(DATE(2024,3,15)) = 15

**The EOMONTH Function**
- **Syntax**: `=EOMONTH(start_date, months)`
- **Purpose**: Return last day of month (useful for reporting)
- **Example**: EOMONTH(TODAY(), 0) = last day of current month

**The DATEDIF Function**
- **Syntax**: `=DATEDIF(start_date, end_date, unit)`
- **Purpose**: Calculate difference between dates
- **Units**: "Y" (years), "M" (months), "D" (days)
- **Example**: DATEDIF(hire_date, TODAY(), "Y") = employee tenure in years

### Business Applications of Date Functions

**Employee Tenure Calculation**
```
=DATEDIF(hire_date, TODAY(), "Y") & " years, " & DATEDIF(hire_date, TODAY(), "YM") & " months"
```

**Age from Birth Date**
```
=DATEDIF(birth_date, TODAY(), "Y")
```

**Days Overdue**
```
=IF(TODAY() > due_date, DATEDIF(due_date, TODAY(), "D"), 0)
```

**Month-End Reporting**
```
=IF(TODAY() = EOMONTH(TODAY(), 0), "Run monthly report", "Not month-end yet")
```

### Conditional Formatting

**Purpose**: Highlight cells based on their values or conditions

**Common Uses**
- Highlight errors (#DIV/0!, #N/A, etc.)
- Highlight duplicates
- Highlight top/bottom values
- Highlight cells outside expected range
- Highlight missing values (blank cells)

**How It Works**
- Define a rule
- Apply a format (color, font, icon)
- Excel automatically applies format to cells matching rule

**Benefits**
- Visual data quality indicators
- Quickly spot problems in large datasets
- Professional-looking reports
- Guides user attention to key issues

### Common Mistakes to Avoid

- IFERROR hiding real problems (use carefully, not everywhere)
- Wrong date format causing calculation errors
- Not understanding date serial number system
- Conditional formatting rules that overlap or conflict
- Applying formatting to wrong range

### Key Questions to Answer

1. When is IFERROR appropriate vs when should you investigate the error?
2. How do you calculate age or tenure using date functions?
3. What does conditional formatting reveal about data quality?
4. How do you combine IFERROR with date functions?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Error-Resilient Lookup**
- Create a customer master table
- Create a sales data table with some invalid customer IDs
- Use IFERROR with VLOOKUP to retrieve customer names
- Display "Unknown Customer" for missing matches

**Exercise 2: Employee Analytics with Dates**
- Create employee dataset with hire dates
- Calculate tenure in years using DATEDIF
- Calculate age if birth date available
- Use IF to flag employees due for benefits review (tenure ≥ 5 years)

**Exercise 3: Invoice Aging Report**
- Create invoice dataset with due dates
- Use DATEDIF to calculate days overdue
- Use IFERROR to handle blank dates
- Apply conditional formatting to highlight:
  - Overdue invoices (red)
  - Due today (yellow)
  - Not yet due (green)

**Exercise 4: Month-End Calculations**
- Use EOMONTH to calculate month-end dates
- Calculate month-over-month changes
- Use TODAY() for dynamic date references
- Build formulas that always use current month

**Exercise 5: Complete Data Quality Dashboard**
- Build a report with:
  - Customer data with error-handled lookups
  - Employee tenure calculations
  - Invoice aging analysis
- Apply conditional formatting throughout
- Add summary statistics
- Document assumptions and formulas

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain how IFERROR improves reporting quality?
- [ ] Can you build date-based calculations confidently?
- [ ] Can you design conditional formatting rules for data quality?
- [ ] Can you combine error handling with business logic?

### Documentation Task
Write a brief explanation (300-400 words) of:
- How you would approach building an error-resilient report
- Explanation of date calculations in your business context
- How conditional formatting guides user focus

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand common error types in Excel
- [ ] Understand IFERROR syntax and purpose
- [ ] Know when to use IFERROR appropriately
- [ ] Understand how Excel stores and displays dates
- [ ] Understand TODAY, YEAR, MONTH, DAY, DATEDIF functions
- [ ] Know how to apply conditional formatting rules

**Hands-On Practice**
- [ ] Created error-handled lookup formula
- [ ] Calculated employee tenure from hire dates
- [ ] Built invoice aging report with date calculations
- [ ] Applied conditional formatting for visual insights
- [ ] Built complete data quality dashboard

**Documentation**
- [ ] Documented error handling approach
- [ ] Explained date calculation logic
- [ ] Reflected on report quality improvements

---

## 📖 Reference Resources

- Excel IFERROR function documentation
- Excel date functions and serial number system
- Conditional formatting rules and best practices
- Real business reporting examples

---

## 🎯 Next Steps

Tomorrow (Day 5) you'll consolidate everything by learning data cleansing methodology and applying it to complete datasets. Today's error handling and date functions are key components of professional data preparation.
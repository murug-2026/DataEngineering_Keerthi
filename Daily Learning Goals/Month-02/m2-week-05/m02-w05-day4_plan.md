# 📙 Day 4 — Validity & Data Validation

## Learning Objectives
By the end of this day, you should be able to:
- Understand validity as a data quality dimension
- Define what makes data "valid" in business context
- Design data validation rules for different data types
- Implement validation checks in Excel
- Create validation reports

---

## 📚 Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What is Validity?**
- **Definition**: Does the data conform to required formats, ranges, and business rules?
- **Questions**:
  - Is the data the right type? (number, text, date)
  - Is it in the right format? (email format, date format)
  - Is it within valid range? (age 0-150, discount 0-100%)
  - Does it follow business rules? (Status in allowed values)
- **Note**: Data can be valid but inaccurate (correctly formatted wrong value)

**Types of Validity Checks**
- **Data type validation**: Is it actually a number? A date?
  - Problem: Numbers stored as text, dates as numbers
  - Check: `=ISNUMBER(A1)`, `=ISTEXT(B1)`, `=IFERROR(DATEVALUE(C1),FALSE)`
- **Format validation**: Does it match expected pattern?
  - Email: Must contain @ and domain
  - Phone: Must be 10 digits (or country-specific format)
  - Postal code: Specific pattern for country
  - Check: `=AND(ISNUMBER(FIND("@",Email)), ISNUMBER(FIND(".",Email)))`
- **Range validation**: Is it within bounds?
  - Age: 0-120 for humans
  - Discount percentage: 0-100%
  - Price: > 0
  - Check: `=AND(A1>=Min, A1<=Max)`
- **List validation**: Is it from allowed values?
  - Status must be: "Active", "Inactive", "Pending"
  - Department must be: "Sales", "IT", "HR", "Finance"
  - Country must be valid 3-letter code
  - Check: `=COUNTIF(AllowedValues, A1) > 0`
- **Pattern/Regex validation**: Does it match expected pattern?
  - SSN format: XXX-XX-XXXX
  - License plate format: State-specific
  - Product code: Specific structure
  - Check: Advanced, uses REGEX or string functions
- **Domain validation**: Is it from a valid lookup table?
  - CustomerID must exist in Customers table
  - ProductID must exist in Products table
  - ManagerID must exist in Employees table
  - Check: `=VLOOKUP(A1, ValidList, 1, FALSE)` returns error if not found
- **Business rule validation**: Does it follow company policies?
  - Discount can't exceed 50% for regular customers
  - Order quantity must be multiple of packaging unit
  - Invoice date must be within 30 days of order date
  - Check: Complex formulas combining multiple conditions

**Invalid Data Patterns**
- **Type mismatches**: 
  - "100" as text when should be number
  - 44956 (Excel serial) when should display as "2023-01-15"
  - TRUE/FALSE as text "True"/"False"
- **Format violations**:
  - "john@gmail" missing .com
  - "(555)123-4567" different format than "5551234567"
  - "15/01/2023" in US system expecting "01/15/2023"
- **Out-of-range values**:
  - Age -5 or 300
  - Discount 150%
  - Revenue $-1000 for completed sale
- **Not-in-list errors**:
  - Status "Pnding" instead of "Pending" (typo)
  - Department "Sls" instead of "Sales"
  - Country "USA" instead of "US" code
- **Business rule violations**:
  - Employee started after manager resigned
  - Promotion date before hire date
  - End date before start date

**Sources of Invalid Data**
- **Data entry errors**: Typos, wrong field, accidental key presses
- **System configuration**: Wrong data type defined in database
- **Legacy data**: Old system had no validation
- **User workarounds**: People bypass validation to work around issues
- **Upstream quality**: Data received invalid from source
- **System updates**: Business rules changed, old data now invalid

**Business Scenarios**
1. **Financial**: Account numbers must follow specific format, transaction amounts must be positive
2. **Healthcare**: Patient age must be realistic, medication codes must exist in formulary
3. **E-commerce**: Product prices > 0, email addresses must be valid format, countries from allowed list
4. **HR**: Employee ID format, salary ranges by position, hire date before termination date
5. **Telecommunications**: Phone numbers specific format, account numbers specific length

**Validation Rule Hierarchy**
1. **Critical**: Reject entire record if violated (customer ID, order amount)
2. **Important**: Flag for review (customer email format)
3. **Minor**: Log but don't prevent use (preferred spelling variation)
- Different systems have different requirements

**Key Questions to Explore**
1. What makes data "valid" for your specific business?
2. How would you distinguish between invalid and inaccurate?
3. What validation rules are non-negotiable?
4. How would you handle borderline cases?
5. What's the cost of accepting invalid data?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Identify Invalid Data**
- Provided dataset: Mixed-quality customer and order records
- Tasks:
  - Check data types (are numbers actually numbers?)
  - Verify email format (contains @ and domain)
  - Check age within valid range
  - Verify status values are from allowed list
  - Verify dates are in correct format
  - Identify all invalid records

**Exercise 2: Build Validation Formulas**
- Create validation columns for:
  - Type check: `=IF(ISNUMBER(Price), "Valid", "Invalid: Not a number")`
  - Range check: `=IF(AND(Age>=18, Age<=120), "Valid", "Invalid: Out of range")`
  - List check: `=IF(COUNTIF({"Active","Inactive"}, Status)>0, "Valid", "Invalid: Not in allowed values")`
  - Format check: `=IF(AND(LEN(Email)>5, ISNUMBER(FIND("@", Email))), "Valid", "Invalid: Email format")`
  - Lookup check: `=IF(ISERROR(VLOOKUP(DeptID, Departments, 1, FALSE)), "Invalid: Dept not found", "Valid")`

**Exercise 3: Create Validation Report**
- Build report showing:
  - Field name
  - Validation rule applied
  - Count of valid records
  - Count of invalid records
  - % validity score
  - Sample of invalid values
- Identify which fields have worst validity

**Exercise 4: Design Validation Strategy**
- For sample business dataset:
  - Define validity rules for each field
  - Classify rules as critical/important/minor
  - Decide: Reject or flag invalid records?
  - Create rules using Excel formulas
  - Apply to test dataset
  - Produce validation summary

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain the difference between invalid and inaccurate?
- [ ] How would you design validation for a complex business process?
- [ ] What's more important: catching all invalid data or avoiding false positives?
- [ ] How would you communicate validation results to stakeholders?

### Documentation Task
Write a brief explanation (300-400 words) covering:
- Types of validity checks and when to use each
- How validity differs from accuracy and completeness
- How you would implement validation for a specific business scenario

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand validity as a data quality dimension
- [ ] Know types of validity checks (type, format, range, list, pattern, domain, business rule)
- [ ] Understand common invalid data patterns
- [ ] Know sources of invalid data
- [ ] Understand validation rule hierarchies (critical, important, minor)
- [ ] Know how to distinguish validity from accuracy

**Hands-On Practice**
- [ ] Identified invalid data in sample dataset by type
- [ ] Built validation formulas for different data types
- [ ] Applied validation to dataset and captured results
- [ ] Created validation report with metrics
- [ ] Designed validation strategy for complex scenario
- [ ] Applied validation rules and documented violations

**Documentation**
- [ ] Documented validation rules clearly
- [ ] Explained how each rule supports business requirements
- [ ] Reflected on validation challenges

---

## 📖 Reference Resources

- Validity check types and implementations
- Excel validation formula patterns
- Data type detection functions
- Format validation techniques
- Business rule validation examples
- Validation report structure

---

## 🎯 Next Steps

Tomorrow (Day 5) you'll learn about **Duplicates and Uniqueness** — identifying and handling duplicate records, understanding why they occur, and strategies for deduplication and entity resolution.

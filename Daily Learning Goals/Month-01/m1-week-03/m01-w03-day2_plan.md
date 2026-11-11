# 📗 Day 2 — Text Functions: LEFT, RIGHT, MID, LEN

## Learning Objectives
By the end of this day, you should be able to:
- Extract specific portions of text using LEFT, RIGHT, and MID functions
- Calculate string lengths using LEN
- Parse business data codes and identifiers
- Combine text functions with other Excel operations

---

## 📚 Conceptual Understanding (3 hours)

### Core Concepts to Learn

**Text Strings in Excel**
- Text is stored as sequences of characters
- Each character has a position (1st, 2nd, 3rd, etc.)
- Text functions navigate and extract based on position

**The LEFT Function**
- **Syntax**: `=LEFT(text, num_chars)`
- **Purpose**: Extract first N characters from left side
- **Example**: LEFT("2023-Customer-001", 4) = "2023"
- **Business Use**: Extract year from date, extract code prefix

**The RIGHT Function**
- **Syntax**: `=RIGHT(text, num_chars)`
- **Purpose**: Extract last N characters from right side
- **Example**: RIGHT("2023-Customer-001", 3) = "001"
- **Business Use**: Extract sequence number, extract suffix

**The MID Function**
- **Syntax**: `=MID(text, start_num, num_chars)`
- **Purpose**: Extract characters from middle of text
- **Example**: MID("2023-Customer-001", 6, 8) = "Customer"
- **Business Use**: Extract department code, product category from complex IDs

**The LEN Function**
- **Syntax**: `=LEN(text)`
- **Purpose**: Return the length (number of characters)
- **Example**: LEN("Customer") = 8
- **Business Use**: Validate ID format, detect data quality issues

### Business Applications

**Customer ID Parsing**
- ID format: "DEPT-YEAR-SEQ" (e.g., "ENG-2023-1001")
- Extract department: LEFT(id, 3)
- Extract year: MID(id, 5, 4)
- Extract sequence: RIGHT(id, 4)

**Phone Number Formatting**
- Extract area code: LEFT(phone, 3)
- Extract last 4 digits: RIGHT(phone, 4)
- Format as (XXX) XXX-XXXX

**Product SKU Parsing**
- SKU format: "BRAND-CATEGORY-COLOR-SIZE" (e.g., "ADI-SHOE-BLK-42")
- Extract brand: LEFT(sku, 3)
- Extract category: MID(sku, 5, 4)
- etc.

### Text Functions with Different Data Types
- Numbers stored as text: Functions work, but comparison issues arise
- Dates as text: Difficult to work with dates functions later
- Empty cells: LEN returns 0

### Common Mistakes to Avoid
- Wrong start position in MID (starts at 1, not 0)
- Wrong number of characters requested
- Using MID when LEFT or RIGHT would be simpler
- Not accounting for spaces in position counting

### Key Questions to Answer

1. How do you extract the first 5 characters of a product code?
2. How would you extract the middle portion of an ID?
3. What's the difference between using MID vs LEFT/RIGHT?
4. How do you validate that text has expected length?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Name Parsing**
- Dataset: Full names in format "FirstName LastName"
- Extract first name using LEFT
- Extract last name using RIGHT
- Determine where to split using LEN

**Exercise 2: Customer ID Extraction**
- Dataset: Customer IDs "CUST-2023-12345"
- Extract customer prefix: LEFT(id, 4)
- Extract year: MID(id, 6, 4)
- Extract sequence: RIGHT(id, 5)
- Create descriptions using extracted values

**Exercise 3: Product Code Parsing**
- Dataset: SKU codes "BRAND-CAT-COLOR-SIZE"
- Extract and separate each component
- Create human-readable product descriptions
- Flag any codes that don't match expected pattern using LEN

**Exercise 4: Data Validation**
- Create formulas to validate:
  - Phone numbers are 10 digits
  - Product codes are exactly 20 characters
  - Email addresses contain @ symbol
- Flag invalid records

**Exercise 5: Complete Data Parser**
- Build a customer record parser that extracts:
  - Name components
  - ID components
  - Contact information components
- Create a clean, parsed dataset

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you extract any part of a string using LEFT/RIGHT/MID?
- [ ] Can you identify text stored incorrectly or with quality issues?
- [ ] Can you design a parsing logic for complex business codes?
- [ ] Can you validate text field integrity using LEN?

### Documentation Task
Write a brief explanation (300-400 words) of:
- How you would parse a complex ID or code in your business
- Steps in creating a reliable text extraction formula
- How text functions support data quality validation

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand LEFT function and use cases
- [ ] Understand RIGHT function and use cases
- [ ] Understand MID function with start and length
- [ ] Understand LEN function for validation
- [ ] Know how positions are counted (starting at 1)
- [ ] Identify where text functions fail (wrong position, wrong length)

**Hands-On Practice**
- [ ] Extracted first/last names from full names
- [ ] Parsed customer IDs into components
- [ ] Parsed product codes into components
- [ ] Validated text field lengths and content
- [ ] Built a complete data parser

**Documentation**
- [ ] Documented parsing logic clearly
- [ ] Explained use of each text function
- [ ] Reflected on quality validation approach

---

## 📖 Reference Resources

- Excel text function documentation
- Real business code/ID formats
- Text extraction examples
- Data validation techniques

---

## 🎯 Next Steps

Tomorrow (Day 3) you'll learn how to clean text data using TRIM, UPPER, LOWER, PROPER, and SUBSTITUTE. Today's extraction functions will combine with tomorrow's cleaning functions for complete data preparation.
# 📙 Day 3 — TRIM, UPPER, LOWER, PROPER, SUBSTITUTE

## Learning Objectives
By the end of this day, you should be able to:
- Clean dirty text data using TRIM, UPPER, LOWER, and PROPER
- Replace characters and patterns using SUBSTITUTE
- Standardize text formatting for data quality
- Build complete text cleaning pipelines

---

## 📚 Conceptual Understanding (3 hours)

### Understanding Dirty Text Data

**Common Text Quality Issues**
- **Extra spaces**: "  Customer  Name  " (leading, trailing, multiple)
- **Wrong casing**: "JOHN DOE", "john doe", "JoHn DoE"
- **Inconsistent formatting**: Mixed case in same field
- **Wrong characters**: Special characters, typos, encoding issues
- **Missing standardization**: Different formats for same data type

**Why Text Cleaning Matters**
- Lookups fail with extra spaces
- Text comparisons fail with wrong casing
- Reports look unprofessional with inconsistent formatting
- Data quality issues cascade through analysis

### The TRIM Function
- **Syntax**: `=TRIM(text)`
- **Purpose**: Remove extra spaces
  - Removes leading spaces (before text)
  - Removes trailing spaces (after text)
  - Reduces multiple spaces between words to single space
- **Example**: TRIM("  Customer  Name  ") = "Customer Name"
- **Limitation**: Does NOT remove non-breaking spaces or special whitespace

**When to Use TRIM**
- Cleaning imported data from other systems
- Data from copy-paste operations
- Preparing for VLOOKUP or text comparisons

### The UPPER Function
- **Syntax**: `=UPPER(text)`
- **Purpose**: Convert all text to UPPERCASE
- **Example**: UPPER("Customer Name") = "CUSTOMER NAME"
- **Business Use**: Standardize codes, enforce consistency

### The LOWER Function
- **Syntax**: `=LOWER(text)`
- **Purpose**: Convert all text to lowercase
- **Example**: LOWER("Customer Name") = "customer name"
- **Business Use**: Standardize email addresses, normalize data

### The PROPER Function
- **Syntax**: `=PROPER(text)`
- **Purpose**: Convert text to Title Case (first letter capitalized, rest lowercase)
- **Example**: PROPER("john DOE") = "John Doe"
- **Business Use**: Standardize customer names, product names
- **Important**: Never use PROPER on codes or product IDs (it will change them!)

### The SUBSTITUTE Function
- **Syntax**: `=SUBSTITUTE(text, old_text, new_text, [instance_num])`
- **Purpose**: Replace specific text or characters
- **Example**: SUBSTITUTE("John-Doe", "-", " ") = "John Doe"
- **Case Sensitive**: "A" and "a" are treated as different
- **Replace Specific Instance**: Use instance_num to replace only certain occurrence

### Combining Cleaning Functions

**Complete Cleaning Pipeline**
```
Dirty Data
   ↓
TRIM (remove extra spaces)
   ↓
UPPER/LOWER/PROPER (standardize case)
   ↓
SUBSTITUTE (fix characters)
   ↓
Clean Data
```

**Example: Cleaning Customer Names**
- Raw: "  JOHN   doe  "
- Step 1: =TRIM(A1) → "JOHN   doe"
- Step 2: =PROPER(TRIM(A1)) → "John Doe"
- Result: Standardized name

### Common Mistakes to Avoid

- Using CLEAN instead of TRIM (CLEAN removes special characters, TRIM removes spaces)
- Using SUBSTITUTE case-sensitively when you need case-insensitive
- Applying PROPER to codes/IDs (destroys them!)
- Not considering the order of operations in cleaning pipelines
- TRIM only works on standard spaces, not all whitespace characters

### Key Questions to Answer

1. When would you use each cleaning function?
2. What's the correct order to combine multiple cleaning functions?
3. Why should you never use PROPER on product codes?
4. How do you replace multiple different characters?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Customer Name Cleaning**
- Dataset: Messy customer names with extra spaces and inconsistent casing
- Apply TRIM + PROPER to clean
- Test with edge cases (multiple spaces, unusual capitalization)

**Exercise 2: Email Address Standardization**
- Dataset: Email addresses with varying case
- Use LOWER to standardize all emails
- Combine with TRIM for spaces

**Exercise 3: Product Code Cleaning**
- Dataset: Product codes with dashes/underscores mixed inconsistently
- Use SUBSTITUTE to normalize separator characters
- Be careful NOT to use PROPER on codes

**Exercise 4: Description Field Cleaning**
- Dataset: Product descriptions with:
  - Extra spaces
  - Inconsistent casing
  - Special character formatting
- Build cleaning pipeline: TRIM → PROPER → SUBSTITUTE
- Create human-readable descriptions

**Exercise 5: Complete Data Cleaning Pipeline**
- Build a customer database cleaning workbook with:
  - Customer names (TRIM + PROPER)
  - Email addresses (LOWER + TRIM)
  - Phone numbers (SUBSTITUTE for formatting)
  - Product descriptions (full pipeline)
- Document each cleaning step
- Show before/after comparison

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you clean any text field using these functions?
- [ ] Can you identify which cleaning function is appropriate for a problem?
- [ ] Can you build a multi-step cleaning pipeline?
- [ ] Can you explain why cleaning order matters?

### Documentation Task
Write a brief explanation (300-400 words) of:
- Your approach to cleaning a complex messy dataset
- Why cleaning functions must be applied in specific order
- Real examples from your industry/domain

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand TRIM function and its limitations
- [ ] Understand UPPER, LOWER, PROPER functions
- [ ] Know when to use PROPER vs UPPER/LOWER
- [ ] Understand SUBSTITUTE syntax and use
- [ ] Understand why cleaning order matters
- [ ] Know common mistakes (PROPER on codes, wrong order)

**Hands-On Practice**
- [ ] Cleaned customer names with TRIM + PROPER
- [ ] Standardized email addresses with LOWER
- [ ] Cleaned product codes without damaging them
- [ ] Created multi-step cleaning pipelines
- [ ] Built complete data cleaning workbook

**Documentation**
- [ ] Documented each cleaning step
- [ ] Explained cleaning logic clearly
- [ ] Reflected on data quality improvements

---

## 📖 Reference Resources

- Excel text cleaning functions
- Data quality standards and definitions
- Before/after cleaning examples
- Text normalization best practices

---

## 🎯 Next Steps

Tomorrow (Day 4) you'll learn IFERROR to handle errors gracefully, plus date functions for time-based analysis. Today's text cleaning will make tomorrow's error handling and date functions more reliable.
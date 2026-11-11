# 📗 Day 2 — XLOOKUP and VLOOKUP

## Learning Objectives
By the end of this day, you should be able to:
- Apply VLOOKUP for vertical lookups in structured tables
- Apply XLOOKUP for flexible lookups in any direction
- Handle exact and approximate matches
- Fix common lookup errors and edge cases
- Choose appropriate lookup function for the task

---

## 📚 Conceptual Understanding (3 hours)

### The VLOOKUP Function

**Syntax**: `=VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])`

**Parameters Explained**
- **lookup_value**: What you're searching for (usually from another cell)
  - Example: Customer ID = "CUST-001"
- **table_array**: The range containing the lookup table
  - Must include lookup column AND return column
  - Example: $A$2:$D$100 (entire customer master)
- **col_index_num**: Which column to return (counting from left)
  - First column in range = 1, second = 2, etc.
  - Example: If looking in column A, returning column D: col_index = 4
- **range_lookup**: Exact or approximate match
  - FALSE or 0 = Exact match (most common in business)
  - TRUE or 1 = Approximate match (for sorted numerical data)

**Example: Customer Lookup**
```
=VLOOKUP(A2, $C$2:$F$100, 2, 0)
- A2 = Customer ID to search for
- $C$2:$F$100 = Customer master table
- 2 = Return Customer Name (2nd column in range)
- 0 = Exact match required
```

**How VLOOKUP Works**
1. Takes lookup value (A2)
2. Searches first column of table_array for match
3. If found, returns value from col_index column
4. If not found, returns #N/A error

**Advantages of VLOOKUP**
- Standard Excel function (widely known)
- Works in older Excel versions
- Efficient for large tables
- Familiar to most analysts

**Limitations of VLOOKUP**
- Can only look RIGHT (can't retrieve columns to left of lookup column)
- Uses column INDEX number (breaks if columns move)
- Returns first match (problem with duplicates)
- Requires lookup column to be first column
- Error-prone with range_lookup parameter

### The XLOOKUP Function (Modern Alternative)

**Syntax**: `=XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found], [match_mode], [search_mode])`

**Parameters Explained**
- **lookup_value**: What you're searching for
  - Example: Customer ID
- **lookup_array**: Column to search in (just that column)
  - Example: $C$2:$C$100 (only Customer ID column)
- **return_array**: Column to return from (just that column)
  - Example: $F$2:$F$100 (only Customer Name column)
- **if_not_found**: What to return if no match found
  - Example: "Not Found" or "Unknown"
  - Replaces #N/A errors
- **match_mode**: How to match
  - 0 = Exact match (default)
  - -1 = Exact match or next smallest value
  - 1 = Exact match or next largest value
  - 2 = Wildcard match
- **search_mode**: Direction to search
  - 1 = Search first to last (default)
  - -1 = Search last to first

**Example: Customer Lookup with XLOOKUP**
```
=XLOOKUP(A2, $C$2:$C$100, $F$2:$F$100, "Not Found", 0, 1)
- A2 = Customer ID to search for
- $C$2:$C$100 = Column to search (Customer IDs)
- $F$2:$F$100 = Column to return (Customer Names)
- "Not Found" = Return this if no match
- 0 = Exact match
- 1 = Search first to last
```

**Advantages of XLOOKUP**
- Can look in ANY direction (left, right, up, down)
- More flexible with match modes
- Better error handling (if_not_found parameter)
- Column references instead of position (won't break with column movement)
- Clearer syntax (more readable)
- Handles duplicate matches better

**Limitations of XLOOKUP**
- Only available in modern Excel versions (365, newer Excel)
- Not available in older Excel versions
- Learning curve (more complex)

**XLOOKUP vs VLOOKUP: When to Use Which**
- Use VLOOKUP: If you need left-to-right lookup in traditional table
- Use XLOOKUP: If you need flexibility, better error handling, or modern Excel
- Teaching recommendation: Learn XLOOKUP first (better practices)

### Exact vs Approximate Match

**Exact Match (0 or FALSE)**
- Searches for exact value only
- Returns #N/A if not found
- Essential for: Customer IDs, Product codes, any unique identifiers
- **Use in 99% of business scenarios**

**Approximate Match (1 or TRUE)**
- Searches for closest match if exact not found
- REQUIRES sorted data (ascending order)
- Useful for: Tiered pricing, tax brackets, range lookups
- **Use rarely, only when specifically needed**
- Example: Revenue 75000 → Closest match below → Tax rate tier

### Common Lookup Errors

**#N/A Error**
- Cause: Lookup value not found in table
- Solution: Use IFERROR or XLOOKUP's if_not_found parameter
- Prevention: Validate lookup keys before using

**#REF! Error**
- Cause: Reference cell was deleted or moved
- Solution: Use absolute references ($)
- Prevention: Always use $ for table_array

**#VALUE! Error**
- Cause: Data type mismatch (text vs number)
- Solution: Ensure both sides are same type
- Prevention: TRIM and ensure consistent types

**#NAME? Error**
- Cause: Typo in function name
- Solution: Check spelling of VLOOKUP or XLOOKUP
- Prevention: Use formula autocomplete

**Blank Result When Expecting Match**
- Cause: Extra spaces, case differences, hidden characters
- Solution: Use TRIM on both sides before lookup
- Prevention: Clean data thoroughly before lookup

### Data Quality Requirements for Lookups

**For Lookups to Work Reliably**
- ✓ Lookup key must be UNIQUE in master table
- ✓ Lookup key must NOT be BLANK
- ✓ Lookup key must match exactly (case, spaces, format)
- ✓ Data types must match (text to text, number to number)
- ✓ All necessary data must exist (no orphaned records)

**Pre-Lookup Validation**
```
Check for duplicates in master table lookup key
Check for blanks in master table lookup key
Check for extra spaces (use TRIM)
Check data types match
Verify lookup keys from transaction table exist in master table
```

### Key Questions to Answer

1. Why is VLOOKUP limited compared to XLOOKUP?
2. When would you use approximate match vs exact match?
3. How do you prevent #N/A errors in lookups?
4. What data quality issues break lookups?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercise: Building Customer and Product Lookups

**Part 1: Prepare Master Tables (15 minutes)**

Using your Week 4 Day 1 datasets:
- Verify Customer Master has no duplicate IDs
- Verify Product Master has no duplicate IDs
- Clean any extra spaces from keys using TRIM
- Ensure no blank keys
- Document what you checked

**Part 2: VLOOKUP Practice (20 minutes)**

In Sales Transaction table, add new columns:
- Customer Name: =VLOOKUP(B2, $C$2:$D$15, 2, 0)
  - B2 = Customer ID from sales row
  - C2:D15 = Customer Master table
  - Return 2nd column = Name
- Product Price: =VLOOKUP(C2, $G$2:$I$20, 3, 0)
  - C2 = Product ID from sales row
  - G2:I20 = Product Master table
  - Return 3rd column = Price

Test with different customer/product IDs

**Part 3: XLOOKUP Practice (15 minutes)**

In same Sales Transaction table, add XLOOKUP versions:
- Customer Name (XLOOKUP): =XLOOKUP(B2, $C$2:$C$15, $D$2:$D$15, "Unknown")
  - More readable than VLOOKUP
  - Handles missing data better
- Product Price (XLOOKUP): =XLOOKUP(C2, $G$2:$G$20, $I$2:$I$20, "N/A")

Compare VLOOKUP vs XLOOKUP results

**Part 4: Testing & Error Handling (20 minutes)**

Test different scenarios:
- Valid lookup: Returns correct value
- Missing customer: Returns #N/A (VLOOKUP) or "Unknown" (XLOOKUP)
- Duplicate in master: Shows first match
- Case difference: May not match (highlighting data issue)
- Extra space: May not match (highlighting data issue)

Add IFERROR around VLOOKUP:
```
=IFERROR(VLOOKUP(B2, $C$2:$D$15, 2, 0), "Not Found")
```

**Part 5: Build Complete Lookup Report (10 minutes)**

Create sheet showing:
- Sales data with original IDs
- Looked-up customer names
- Looked-up product prices
- Calculated total value (quantity × price)
- Professional formatting

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain why XLOOKUP is more flexible than VLOOKUP?
- [ ] Can you fix lookup errors confidently?
- [ ] Can you validate data before performing lookups?
- [ ] Can you choose between exact and approximate match?

### Documentation Task
Create a 400-word document comparing VLOOKUP and XLOOKUP:
- Explain syntax differences
- Describe when to use each
- Explain advantages and limitations
- Provide real business examples

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand VLOOKUP syntax and limitations
- [ ] Understand XLOOKUP syntax and advantages
- [ ] Know difference between exact and approximate match
- [ ] Understand common lookup errors
- [ ] Know data quality requirements for lookups
- [ ] Can identify which function to use for which task

**Hands-On Practice**
- [ ] Validated master tables before lookup
- [ ] Created working VLOOKUP formulas
- [ ] Created working XLOOKUP formulas
- [ ] Tested with valid and invalid lookups
- [ ] Added error handling
- [ ] Built complete lookup report

**Documentation**
- [ ] Documented VLOOKUP vs XLOOKUP comparison
- [ ] Explained each lookup in your report
- [ ] Reflected on data quality issues found

---

## 📖 Reference Resources

- VLOOKUP and XLOOKUP function documentation
- Exact vs approximate match use cases
- Common lookup errors and solutions
- Data validation before lookup

---

## 🎯 Next Steps

Tomorrow (Day 3) you'll learn INDEX and MATCH functions - an even more powerful alternative to VLOOKUP that can perform two-way lookups. Today's XLOOKUP/VLOOKUP foundation is essential.
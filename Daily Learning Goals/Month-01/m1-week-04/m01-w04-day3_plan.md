# 📙 Day 3 — INDEX and MATCH (Advanced Lookups)

## Learning Objectives
By the end of this day, you should be able to:
- Understand INDEX and MATCH functions individually
- Combine INDEX and MATCH for powerful lookups
- Perform two-way lookups (row and column)
- Replace VLOOKUP with INDEX+MATCH for flexibility
- Handle complex lookup scenarios

---

## 📚 Conceptual Understanding (3 hours)

### The INDEX Function

**Syntax**: `=INDEX(array, row_num, [col_num])`

**Parameters Explained**
- **array**: The range of cells to search in
  - Example: $A$1:$D$100 (entire table)
- **row_num**: Which row to return (1 for first row, 2 for second, etc.)
  - Example: 5 returns 5th row's data
- **col_num**: Which column to return (optional, needed for 2D arrays)
  - Example: 3 returns 3rd column's data
  - If not specified, returns entire row

**Example: Retrieving Customer Name**
```
=INDEX($C$2:$D$100, 5, 2)
- Returns 5th row, 2nd column
- From Customer Master table
- Gets customer name from row 5
```

**How INDEX Works**
- Takes a range
- Finds position (row, column)
- Returns value at that position
- Does NOT search or match anything
- You specify exact row/column position

### The MATCH Function

**Syntax**: `=MATCH(lookup_value, lookup_array, [match_type])`

**Parameters Explained**
- **lookup_value**: What you're searching for
  - Example: Customer ID "CUST-001"
- **lookup_array**: Column (or row) to search in
  - Example: $C$2:$C$100 (Customer ID column)
- **match_type**: How to match
  - 0 = Exact match (most common)
  - 1 = Less than (requires sorted ascending)
  - -1 = Greater than (requires sorted descending)

**Example: Finding Customer Position**
```
=MATCH("CUST-001", $C$2:$C$100, 0)
- Searches for "CUST-001" in range
- Returns row NUMBER (position)
- Example: Returns 5 if found in 5th row of range
```

**How MATCH Works**
- Searches for value in array
- Returns POSITION (row number)
- Does NOT return the value itself
- Only returns position/index

### Combining INDEX and MATCH

**Why Combine Them?**
- INDEX finds data at a position
- MATCH finds the position
- Together: Find position, then retrieve data
- More powerful than VLOOKUP

**Syntax**: `=INDEX(return_array, MATCH(lookup_value, lookup_array, 0))`

**Example: Customer Lookup**
```
=INDEX($D$2:$D$100, MATCH(A2, $C$2:$C$100, 0))
- MATCH(A2, $C$2:$C$100, 0) → Finds row position of Customer ID
- INDEX($D$2:$D$100, ...) → Returns Customer Name from that position
```

**How INDEX+MATCH Works Step-by-Step**
1. Inner formula (MATCH) executes first
   - Searches for lookup value
   - Returns row position
2. Outer formula (INDEX) executes next
   - Uses position from MATCH
   - Returns value at that position

### Advantages Over VLOOKUP

**INDEX+MATCH vs VLOOKUP**
- Can look LEFT or RIGHT (any direction)
- Return column independent of lookup column
- More readable (explicit which column to return)
- Handles duplicates differently
- Smaller performance impact on large files

**Real Example: Product Pricing Lookup**
```
VLOOKUP Limitation:
- Must put lookup column on LEFT
- Must put price on RIGHT
- Price in column 3? Use col_index=3
- If column order changes, formula breaks

INDEX+MATCH Solution:
=INDEX($F$2:$F$100, MATCH(A2, $C$2:$C$100, 0))
- Searches Product ID in column C
- Returns Price from column F
- Works regardless of column order
```

### Two-Way Lookups

**What is Two-Way Lookup?**
- Find value based on row AND column
- Example: Find price for Product X in Region Y
- Combines INDEX+MATCH on both dimensions

**Syntax**: `=INDEX(return_array, MATCH(row_value, row_array, 0), MATCH(col_value, col_array, 0))`

**Example: Price Matrix**
```
Products as columns, Regions as rows, Prices in grid
=INDEX($B$2:$E$5, MATCH(F2, $A$2:$A$5, 0), MATCH(G2, $B$1:$E$1, 0))
- MATCH(F2, $A$2:$A$5, 0) → Finds region row
- MATCH(G2, $B$1:$E$1, 0) → Finds product column
- INDEX returns price at that intersection
```

### Common Mistakes to Avoid

- MATCH returning row position but INDEX array starting at different row
  - Solution: Ensure both start at same row
- Confusing what MATCH returns (position, not value)
- Using approximate match when exact match needed
- Two-way lookups with incorrect array references

### Key Questions to Answer

1. Why is INDEX+MATCH more flexible than VLOOKUP?
2. How do you perform two-way lookups?
3. When would you use approximate match in MATCH?
4. What happens if MATCH doesn't find value?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercise: INDEX+MATCH Lookups

**Part 1: Basic INDEX+MATCH (20 minutes)**

Using Week 4 Day 1 datasets:
- Replace VLOOKUP with INDEX+MATCH for customer lookup
- Replace VLOOKUP with INDEX+MATCH for product lookup
- Verify results match VLOOKUP (should be identical)

Formula:
```
Customer: =INDEX($D$2:$D$15, MATCH(B2, $C$2:$C$15, 0))
Product: =INDEX($I$2:$I$20, MATCH(C2, $G$2:$G$20, 0))
```

**Part 2: Multi-Column Return (20 minutes)**

Create new scenario:
- Need to return multiple pieces of information
- Example: Product lookup returns (Name, Price, Supplier)
- Create formulas for each:
  - INDEX for column 1 (Name)
  - INDEX for column 2 (Price)
  - INDEX for column 3 (Supplier)

**Part 3: Two-Way Lookup (20 minutes)**

Create price matrix:
- Products in columns (Shoes, Hats, Gloves)
- Regions in rows (North, South, East)
- Prices in grid (different price per region/product)

Build formula:
```
=INDEX($B$2:$E$5, MATCH(F2, $A$2:$A$5, 0), MATCH(G2, $B$1:$E$1, 0))
```

Test with different region/product combinations

**Part 4: Error Handling (10 minutes)**

Add error handling:
```
=IFERROR(INDEX(..., MATCH(..., 0)), "Not Found")
```

Test with valid and invalid lookups

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain INDEX+MATCH to a beginner?
- [ ] Can you perform two-way lookups confidently?
- [ ] Can you troubleshoot INDEX+MATCH errors?
- [ ] Can you choose between VLOOKUP, XLOOKUP, and INDEX+MATCH?

### Documentation Task
Create a 400-word document:
- Explaining how INDEX and MATCH work together
- Showing advantage over VLOOKUP with example
- Explaining two-way lookup with real business case

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand INDEX function syntax
- [ ] Understand MATCH function syntax
- [ ] Understand how INDEX and MATCH work together
- [ ] Know why INDEX+MATCH is more flexible
- [ ] Understand two-way lookups
- [ ] Identify when to use INDEX+MATCH

**Hands-On Practice**
- [ ] Created basic INDEX+MATCH lookups
- [ ] Returned multiple columns with INDEX
- [ ] Built two-way lookup matrix
- [ ] Added error handling
- [ ] Tested various scenarios

---

## 🎯 Next Steps

Tomorrow (Day 4) you'll learn conditional aggregation functions (SUMIFS, COUNTIFS, AVERAGEIFS) to combine data from multiple tables with conditions.
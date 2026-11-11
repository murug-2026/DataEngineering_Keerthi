# 📕 Day 4 — SUMIFS, COUNTIFS, AVERAGEIFS

## Learning Objectives
By the end of this day, you should be able to:
- Understand conditional aggregation functions
- Apply SUMIFS for multi-criteria summation
- Apply COUNTIFS for multi-criteria counting
- Apply AVERAGEIFS for multi-criteria averaging
- Build business performance analysis using conditional functions

---

## 📚 Conceptual Understanding (3 hours)

### Understanding Conditional Aggregation

**What is Conditional Aggregation?**
- Summing/counting/averaging based on criteria
- Instead of ALL data, only data matching conditions
- Example: Total sales for Product X in Region Y
- Essential for business analysis and reporting

**Why Conditional Aggregation Matters**
- Business decisions based on specific segments
- Need to analyze by category, region, time period, etc.
- Raw totals hide important patterns
- Drill-down analysis requires conditions

### The SUMIFS Function

**Syntax**: `=SUMIFS(sum_range, criteria_range1, criteria1, [criteria_range2, criteria2], ...)`

**Parameters Explained**
- **sum_range**: The column to sum (prices, sales amounts, etc.)
  - Example: $F$2:$F$100 (Sales Amount)
- **criteria_range1**: First column to check conditions
  - Example: $B$2:$B$100 (Customer ID)
- **criteria1**: What to match in criteria_range1
  - Example: "CUST-001" (specific customer)
- **criteria_range2, criteria2, ...**: Additional conditions (optional)
  - Example: Region = "North" AND Date > 2024-01-01

**Example: Sales by Region**
```
=SUMIFS($F$2:$F$100, $E$2:$E$100, "North", $D$2:$D$100, ">2024-01-01")
- Sum column F (Sales Amount)
- Where column E (Region) = "North"
- AND column D (Date) > 2024-01-01
```

**How SUMIFS Works**
1. Checks each row in criteria_range1
2. If matches criteria1, includes that row's sum_range value
3. Repeats for all additional criteria
4. Returns total of matching values

**Criteria Operators**
- `=` Equal (exact match)
- `<>` Not equal
- `>` Greater than
- `<` Less than
- `>=` Greater than or equal
- `<=` Less than or equal
- Wildcards: `*` any characters, `?` single character

### The COUNTIFS Function

**Syntax**: `=COUNTIFS(criteria_range1, criteria1, [criteria_range2, criteria2], ...)`

**Purpose**: Count how many rows meet ALL criteria

**Example: Count of Orders**
```
=COUNTIFS($B$2:$B$100, "CUST-001", $E$2:$E$100, "Shipped")
- Count rows where:
- Customer ID = "CUST-001" (column B)
- AND Status = "Shipped" (column E)
```

**Difference: COUNTIF vs COUNTIFS**
- COUNTIF: Single criterion
- COUNTIFS: Multiple criteria (all must be true)

**Business Uses**
- Count orders by customer
- Count active customers
- Count orders in date range with specific status
- Count items in inventory above threshold

### The AVERAGEIFS Function

**Syntax**: `=AVERAGEIFS(average_range, criteria_range1, criteria1, ...)`

**Purpose**: Calculate average of values matching criteria

**Example: Average Order Value**
```
=AVERAGEIFS($F$2:$F$100, $B$2:$B$100, "CUST-001", $E$2:$E$100, "Completed")
- Average of column F (Order Amount)
- Where Customer ID = "CUST-001"
- AND Status = "Completed"
```

### Comparing Functions

| Function | Count | Sum | Average | Other |
|----------|-------|-----|---------|-------|
| COUNTIF | ✓ | — | — | Single criterion |
| SUMIF | — | ✓ | — | Single criterion |
| COUNTIFS | ✓ | — | — | Multiple criteria |
| SUMIFS | — | ✓ | — | Multiple criteria |
| AVERAGEIF | — | — | ✓ | Single criterion |
| AVERAGEIFS | — | — | ✓ | Multiple criteria |

### Business Applications

**Sales Analysis**
```
Total sales by region
=SUMIFS($F$2:$F$100, $E$2:$E$100, "North")

Orders per customer
=COUNTIFS($B$2:$B$100, "CUST-001")

Average order value
=AVERAGEIFS($F$2:$F$100, $B$2:$B$100, "CUST-001")
```

**Inventory Management**
```
Count items below threshold
=COUNTIFS($D$2:$D$100, "<100")

Total value of high-stock items
=SUMIFS($F$2:$F$100, $D$2:$D$100, ">=500")
```

**Performance Analysis**
```
Sales within date range
=SUMIFS($F$2:$F$100, $C$2:$C$100, ">=2024-01-01", $C$2:$C$100, "<=2024-12-31")

Average for specific product category
=AVERAGEIFS($F$2:$F$100, $E$2:$E$100, "Electronics")
```

### Common Mistakes to Avoid

- Mixing up range order (sum_range vs criteria_range)
- Using >= instead of > (boundary conditions)
- Forgetting quotes around text criteria
- Date format mismatches in criteria
- Multiple criteria that conflict (AND logic, not OR)

### Key Questions to Answer

1. When would you use SUMIFS vs COUNTIFS vs AVERAGEIFS?
2. How do you apply multiple criteria that must ALL be true?
3. How do you create date range criteria (between two dates)?
4. How do you combine conditional functions in reporting?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercise: Building Business Performance Analysis

**Part 1: Sales Summary by Region (20 minutes)**

Using sales data:
- Total sales by region using SUMIFS
- Count of sales by region using COUNTIFS
- Average sale amount by region using AVERAGEIFS

Build formulas:
```
North Sales: =SUMIFS($F$2:$F$100, $E$2:$E$100, "North")
North Count: =COUNTIFS($E$2:$E$100, "North")
North Avg: =AVERAGEIFS($F$2:$F$100, $E$2:$E$100, "North")
```

Repeat for all regions

**Part 2: Sales within Date Range (20 minutes)**

Calculate sales for specific time period:
```
Sales in Q1 2024:
=SUMIFS($F$2:$F$100, $C$2:$C$100, ">=2024-01-01", $C$2:$C$100, "<=2024-03-31")

Orders in Q1:
=COUNTIFS($C$2:$C$100, ">=2024-01-01", $C$2:$C$100, "<=2024-03-31")
```

**Part 3: Multi-Criteria Analysis (20 minutes)**

Combine multiple criteria:
```
Sales for Product X in Region Y:
=SUMIFS($F$2:$F$100, $G$2:$G$100, "Product X", $E$2:$E$100, "Region Y")

Completed orders for specific customer:
=COUNTIFS($B$2:$B$100, "CUST-001", $E$2:$E$100, "Completed")

Average value for Product X that shipped:
=AVERAGEIFS($F$2:$F$100, $G$2:$G$100, "Product X", $E$2:$E$100, "Shipped")
```

**Part 4: Complete Performance Dashboard (20 minutes)**

Build a summary sheet showing:
- Total sales and order count by region
- Average order value by region
- Sales by product with counts
- Regional performance trends
- Top-performing segments

Use conditional formatting to highlight best/worst performers

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you build multi-condition calculations confidently?
- [ ] Can you explain SUMIFS vs COUNTIFS vs AVERAGEIFS clearly?
- [ ] Can you design criteria for complex business questions?
- [ ] Can you build a performance summary using these functions?

### Documentation Task
Create a 400-word document:
- Explaining when to use each function (SUMIFS, COUNTIFS, AVERAGEIFS)
- Providing 3 real business examples
- Explaining multi-criteria AND logic
- Describing how to handle dates in criteria

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand SUMIFS syntax and purpose
- [ ] Understand COUNTIFS syntax and purpose
- [ ] Understand AVERAGEIFS syntax and purpose
- [ ] Know difference between single vs multiple criteria
- [ ] Understand AND logic in multi-criteria
- [ ] Know how to format date criteria

**Hands-On Practice**
- [ ] Created SUMIFS formulas by region
- [ ] Created COUNTIFS formulas by region
- [ ] Created AVERAGEIFS formulas by region
- [ ] Built date range criteria
- [ ] Combined multiple criteria
- [ ] Built performance dashboard

**Documentation**
- [ ] Documented each function and use case
- [ ] Explained business insights from dashboard
- [ ] Reflected on value of conditional aggregation

---

## 🎯 Next Steps

Tomorrow (Day 5) is the final day of Week 4. You'll learn how to bring everything together into professional business reporting using all the skills from this week.
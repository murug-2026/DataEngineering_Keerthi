# Excel Functions

## Q1. What does SUM do?
**Answer:** SUM is an Excel function used to add numerical values and calculate their total.

**Formula:**
```excel
=SUM(B2:B5)
```

**Business uses:** Calculating total sales, expenses, salaries and revenue.

## Q2. What does AVERAGE do?
**Answer:** AVERAGE calculates the arithmetic mean by adding all numerical values and dividing the total by the number of values.

**Formula:**
```excel
=AVERAGE(B2:B5)
```

**Business uses:** Calculating average salaries, monthly sales and customer spending.

## Q3. What is the difference between COUNT and COUNTA?
**Answer:**
- **COUNT:** Counts only cells containing numerical values.
- **COUNTA:** Counts all non-empty cells, including numbers, text and dates.

**Formulas:**
```excel
=COUNT(A2:A10)
=COUNTA(A2:A10)
```

**Business uses:** COUNT measures numerical records, while COUNTA counts completed entries or employee names.

## Q4. What does MIN return?
**Answer:** MIN returns the smallest numerical value in a selected range.

**Formula:**
```excel
=MIN(B2:B10)
```

**Business uses:** Finding the lowest salary, minimum sales or lowest stock quantity.

## Q5. What does MAX return?
**Answer:** MAX returns the largest numerical value in a selected range.

**Formula:**
```excel
=MAX(B2:B10)
```

**Business uses:** Finding the highest salary, maximum sales or highest revenue.

## Q6. How do these functions behave with empty cells, text and errors?

**Answer:**

| Function | Empty cells | Text | Errors |
|---|---|---|---|
| SUM | Ignored | Ignored | Returns error |
| AVERAGE | Ignored | Ignored | Returns error |
| COUNT | Ignored | Ignored | Returns error |
| COUNTA | Not counted | Counted | Returns error |
| MIN | Ignored | Ignored | Returns error |
| MAX | Ignored | Ignored | Returns error |

**Important points:**
- Zero is treated as a numerical value.
- COUNTA counts all non-empty cells.
- Errors in referenced cells generally cause these functions to return an error.

## Q7. How do these functions help in business analysis?

**Answer:**

1. **SUM – Total Sales:** Calculates total sales or revenue.
   ```excel
   =SUM(B2:B30)
   ```
2. **AVERAGE – Average Salary:** Calculates the average salary paid to employees.
   ```excel
   =AVERAGE(C2:C30)
   ```
3. **MIN – Minimum Stock:** Identifies the lowest available stock quantity.
   ```excel
   =MIN(D2:D30)
   ```
4. **MAX – Maximum Revenue:** Identifies the highest revenue generated.
   ```excel
   =MAX(E2:E30)
   ```

These functions help businesses monitor performance, analyse data and make better decisions.

## Q8. What is the difference between AVERAGE, MEDIAN and MODE?

**Answer:**
- **AVERAGE:** Calculates the arithmetic mean of all values.
- **MEDIAN:** Returns the middle value after arranging numbers in order.
- **MODE:** Returns the most frequently occurring value.

**Example:** 10, 20, 20, 30, 40.

| Function | Result |
|---|---:|
| AVERAGE | 24 |
| MEDIAN | 20 |
| MODE | 20 |

**Formulas:**
```excel
=AVERAGE(A2:A6)
=MEDIAN(A2:A6)
=MODE.SNGL(A2:A6)
```

**Business uses:**
- AVERAGE: Analysing overall performance.
- MEDIAN: Analysing typical salaries without extreme values heavily affecting the result.
- MODE: Identifying the most common product size or purchase quantity.

## Q9. How do you combine these functions with references?

**Answer:** Excel functions can be combined with cell references to perform calculations on specific cells or ranges.

**Range references:**
```excel
=SUM(B2:B10)
=AVERAGE(B2:B10)
```

**Individual cell references:**
```excel
=SUM(B2,B4,B6)
=AVERAGE(B2,B4,B6)
```

**Absolute references:**

The dollar sign ($) locks a cell reference when copying formulas.

```excel
=B2*$E$1
```

Here, E1 remains fixed when the formula is copied to other rows.

## Q10. How do these functions behave inside Excel Tables?

**Answer:** Excel Tables support a feature called **Structured References**, which allows users to refer to columns using their names instead of cell addresses.

Suppose the table name is `SalesData` and the column name is `Sales`.

**Examples:**
```excel
=SUM(SalesData[Sales])
=AVERAGE(SalesData[Sales])
=COUNT(SalesData[Sales])
=MIN(SalesData[Sales])
=MAX(SalesData[Sales])
=MEDIAN(SalesData[Sales])
=MODE.SNGL(SalesData[Sales])
```

**Advantages:**
- Automatically includes new records when the table expands.
- Makes formulas easier to understand.
- Reduces errors caused by incorrect cell ranges.
- Helps manage large datasets.
- Supports automatic calculations through the Total Row feature.

## Q11. Why are these functions essential for KPI calculations?

**Answer:** KPI (Key Performance Indicator) is a measurable value used by businesses to evaluate how effectively they are achieving their goals.

| Function | KPI Example | Purpose |
|---|---|---|
| SUM | Total monthly sales | Measures overall sales |
| AVERAGE | Average daily sales | Measures average performance |
| COUNT | Number of transactions | Measures business activity |
| COUNTA | Completed employee records | Measures record completion |
| MIN | Lowest stock quantity | Identifies stock shortages |
| MAX | Highest daily revenue | Identifies peak performance |

These functions help businesses track targets, monitor performance, identify problems and prepare reports and dashboards.

**Important:** A function calculates a metric, while a KPI uses that metric to evaluate progress towards a business goal.


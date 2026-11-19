# Excel – Questions and Answers

## 1. When is IFERROR appropriate vs when should you investigate the error?

**Answer:**

`IFERROR` is used to handle errors in Excel formulas and return a meaningful alternative result instead of displaying an error message.

- **Use IFERROR:** When an error is expected or acceptable, and you want to display a cleaner result.
- **Investigate the error:** When an error indicates a problem with your data, formula, or calculation that needs to be corrected.

**Example:**

```excel
=IFERROR(A2/B2,"Not Available")
```

If B2 contains 0 or is empty, Excel returns "Not Available" instead of `#DIV/0!`.

**Important:** Do not use IFERROR to hide errors that should be corrected. Always understand why an error occurs before handling it.

---

## 2. How do you calculate age or tenure using date functions?

**Answer:**

Excel provides date functions such as `TODAY()` and `DATEDIF()` to calculate age and employee tenure.

### A. Calculate Age

```excel
=DATEDIF(A2,TODAY(),"Y")
```

- A2 contains the date of birth.
- TODAY() returns the current date.
- "Y" calculates the completed years.

### B. Calculate Employee Tenure

```excel
=DATEDIF(B2,TODAY(),"Y")
```

- B2 contains the employee's joining date.
- TODAY() returns the current date.
- "Y" calculates the completed years of service.

### C. Calculate Tenure in Years and Months

```excel
=DATEDIF(B2,TODAY(),"Y")&" Years "&DATEDIF(B2,TODAY(),"YM")&" Months"
```

This returns the employee's completed years and remaining months of service.

---

## 3. What does conditional formatting reveal about data quality?

**Answer:**

Conditional Formatting helps identify patterns, inconsistencies, missing values, and unusual entries in a dataset by automatically applying formatting based on specified conditions.

It helps reveal:

- **Duplicate Values:** Identifies repeated entries in a dataset.
- **Missing Values:** Highlights blank cells.
- **Outliers:** Identifies unusually high or low values.
- **Inconsistent Data:** Highlights values that do not follow expected patterns.
- **Invalid Entries:** Highlights values that do not meet specified conditions.

**Example:**

If employee ages should be between 18 and 60, you can use conditional formatting to highlight ages below 18 or above 60.

This makes data cleaning and error detection easier before performing analysis.

---

## 4. How do you combine IFERROR with date functions?

**Answer:**

You can combine `IFERROR` with date functions such as `DATEDIF()` to handle invalid dates or missing values without displaying Excel error messages.

### Example 1: Calculate Age

```excel
=IFERROR(DATEDIF(A2,TODAY(),"Y"),"Invalid Date")
```

If A2 contains a valid date of birth, Excel calculates the age. Otherwise, it returns "Invalid Date".

### Example 2: Calculate Employee Tenure

```excel
=IFERROR(DATEDIF(B2,TODAY(),"Y"),"Check Joining Date")
```

If the joining date is invalid or creates an error, Excel displays "Check Joining Date".

### Example 3: Handle Blank Dates

```excel
=IF(A2="","Missing Date",IFERROR(DATEDIF(A2,TODAY(),"Y"),"Invalid Date"))
```

This formula:

1. Checks whether the date cell is blank.
2. Returns "Missing Date" if no date is entered.
3. Calculates age if the date is valid.
4. Returns "Invalid Date" if the calculation produces an error.

---

## Quick Revision

| Function / Feature | Purpose |
|---|---|
| `IFERROR()` | Handles formula errors |
| `DATEDIF()` | Calculates the difference between two dates |
| `TODAY()` | Returns the current date |
| Conditional Formatting | Identifies data quality issues visually |

**Key Takeaway:** Understanding errors, calculating date differences, and using conditional formatting are essential skills for maintaining clean and reliable Excel datasets.
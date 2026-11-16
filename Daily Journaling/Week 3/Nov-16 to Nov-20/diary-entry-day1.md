
# Excel Logical Functions and Comparisons

## Q1. When would you use IF vs IFS?

**Answer:**

Both `IF` and `IFS` are used to test conditions and return results based on whether those conditions are met.

- **IF:** Used when checking a single condition and returning one result if TRUE and another if FALSE.
- **IFS:** Used when checking multiple conditions and returning different results for each condition.

### IF Example: Pass or Fail

```excel
=IF(B2>=40,"Pass","Fail")
```

If the marks in B2 are 40 or above, Excel returns `Pass`. Otherwise, it returns `Fail`.

### IFS Example: Student Grades

```excel
=IFS(B2>=90,"A",B2>=70,"B",B2>=40,"C",B2<40,"Fail")
```

| Marks | Grade |
|---|---|
| 95 | A |
| 75 | B |
| 55 | C |
| 30 | Fail |

**Key Difference:** IF is convenient for a single condition or a simple TRUE/FALSE decision. IFS is easier to read when there are several possible outcomes.

---

## Q2. How do AND and OR differ in their logic?

**Answer:**

`AND` and `OR` are logical functions used to test multiple conditions.

- **AND:** Returns TRUE only when all conditions are TRUE.
- **OR:** Returns TRUE when at least one condition is TRUE.

### AND Example: Bonus Eligibility

An employee receives a bonus only if:
- Sales are above ₹50,000.
- Attendance is above 90%.

```excel
=AND(B2>50000,C2>90%)
```

Both conditions must be satisfied for the result to be TRUE.

### OR Example: Reward Eligibility

An employee qualifies for a reward if:
- Sales are above ₹50,000 OR
- Attendance is above 90%.

```excel
=OR(B2>50000,C2>90%)
```

Only one condition needs to be satisfied for the result to be TRUE.

### Difference Between AND and OR

| Feature | AND | OR |
|---|---|---|
| Logic | All conditions must be TRUE | At least one condition must be TRUE |
| Returns TRUE | When every condition is TRUE | When one or more conditions are TRUE |
| Returns FALSE | When at least one condition is FALSE | When all conditions are FALSE |

**Remember:**
- AND = All conditions.
- OR = Any one or more conditions.

---

## Q3. What business rule would require combining IF with AND?

**Answer:**

Combining `IF` with `AND` is useful when a business decision depends on multiple conditions being satisfied simultaneously.

- **AND:** Checks whether all required conditions are TRUE.
- **IF:** Returns the appropriate result based on the outcome of AND.

### Example: Employee Bonus Eligibility

A company gives an employee a bonus only if:

1. Monthly sales are above ₹50,000.
2. Attendance is above 90%.
3. Performance rating is at least 4.

Assume:
- B2 contains monthly sales.
- C2 contains attendance.
- D2 contains the performance rating.

```excel
=IF(AND(B2>50000,C2>90%,D2>=4),"Eligible","Not Eligible")
```

If all three conditions are TRUE, Excel returns `Eligible`. If even one condition is FALSE, it returns `Not Eligible`.

### Other Business Applications

| Business Area | Business Rule |
|---|---|
| Banking | Approve a loan if income and credit score meet minimum requirements. |
| Human Resources | Approve leave if sufficient leave balance exists and the manager approves. |
| Sales | Award commission if sales and customer satisfaction targets are achieved. |
| Inventory | Reorder products if stock is below the minimum level and demand is high. |
| Education | Declare a student eligible if attendance and marks meet minimum requirements. |

**Why is this useful?**

Combining IF with AND helps automate decisions, apply consistent business rules and reduce manual checking.

---

## Q4. Why is text comparison different from number comparison?

**Answer:**

Text comparison and number comparison are different because Excel evaluates text as characters or words, whereas numbers are evaluated as numerical values.

### Text Comparison

Text comparison checks whether words, characters or text strings match.

Example: Check whether an employee belongs to the Sales department.

```excel
=IF(B2="Sales","Eligible","Not Eligible")
```

Excel checks whether the text in B2 matches `Sales`.

**Important Points:**
- Text literals in formulas must be enclosed in double quotation marks.
- Standard Excel text comparisons using `=` are not case-sensitive.
- Extra spaces can cause unexpected mismatches.
- Text values are not compared as numerical quantities.

### Number Comparison

Number comparison checks numerical values using mathematical comparison operators.

Example: Check whether an employee achieved a sales target of ₹50,000.

```excel
=IF(B2>=50000,"Achieved","Not Achieved")
```

Excel compares the numerical value in B2 with 50,000.

### Common Comparison Operators

| Operator | Meaning | Example |
|---|---|---|
| `=` | Equal to | `=A1=100` |
| `>` | Greater than | `=A1>100` |
| `<` | Less than | `=A1<100` |
| `>=` | Greater than or equal to | `=A1>=100` |
| `<=` | Less than or equal to | `=A1<=100` |
| `<>` | Not equal to | `=A1<>100` |

### Difference Between Text and Number Comparison

| Feature | Text Comparison | Number Comparison |
|---|---|---|
| Compares | Words and characters | Numerical values |
| Example | `"Sales"` | `50000` |
| Quotation marks | Used for text literals | Not required for numeric literals |
| Common application | Department or payment-status checks | Sales targets or inventory levels |



# 📘 Day 1 — Logical Functions: IF, IFS, AND, OR

## Learning Objectives
By the end of this day, you should be able to:
- Understand logical conditions and their purpose in Excel
- Apply IF, IFS, AND, and OR functions to real business scenarios
- Build classification and eligibility rules
- Diagnose and fix common logical formula errors

---

## 📚 Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What is a logical condition in Excel?**
- A condition that evaluates to TRUE or FALSE
- Forms the basis of decision-making in spreadsheets

**The IF Function**
- **Syntax**: `=IF(condition, value_if_true, value_if_false)`
- **Purpose**: Test a condition and return different values based on the result
- **Components**:
  - Condition: A comparison or test
  - TRUE branch: What to return if condition is TRUE
  - FALSE branch: What to return if condition is FALSE

**Business Use Cases for IF**
- Classification: High/Medium/Low performance
- Status determination: Active/Inactive accounts
- Eligibility checks: Yes/No decisions
- Discount calculations: Apply discount if criteria met

**The IFS Function**
- Simplifies multiple nested IF statements
- **Syntax**: `=IFS(condition1, value1, condition2, value2, ...)`
- **Advantage over nested IF**: More readable, easier to maintain

**The AND Function**
- Returns TRUE only if ALL conditions are TRUE
- Used to combine multiple criteria that must ALL be satisfied
- **Example**: Active AND verified AND recent activity

**The OR Function**
- Returns TRUE if AT LEAST ONE condition is TRUE
- Used when any single criterion can trigger an action
- **Example**: VIP OR recent_purchase OR referral

**Combining Functions**
- Logical functions work together: IF(AND(...)), IF(OR(...))
- Text vs numbers: Different comparison approaches needed
- Excel Tables: Automatic range expansion

**Common Mistakes to Avoid**
- Missing quotation marks on text comparisons
- Using = instead of <>, >, <, >=, <=
- Incorrect nesting of multiple functions
- Mixing data types in conditions

### Key Questions to Answer

1. When would you use IF vs IFS?
2. How do AND and OR differ in their logic?
3. What business rule would require combining IF with AND?
4. Why is text comparison different from number comparison?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Sales Performance Classification**
- Create a dataset with monthly sales figures
- Use IF to classify as "High" (>50000), "Medium" (20000-50000), or "Low" (<20000)
- Bonus: Use IFS instead

**Exercise 2: Employee Status**
- Create employee records with attendance percentage and tenure
- Use IF to mark as "Good" (attendance >90%) or "Poor" (<90%)
- Create complex rule: "Excellent" if (attendance >95% AND tenure >2 years) OR tenure >5 years

**Exercise 3: Customer Segmentation**
- Build a customer database with purchase history and account age
- Apply rules:
  - "VIP" if (purchase_amount > 10000 AND account_age > 1 year)
  - "New" if account_age <= 3 months
  - "Regular" if otherwise
- Use nested IF or IFS

**Exercise 4: Testing & Troubleshooting**
- Test each formula with edge cases (boundary values)
- Identify and fix intentional errors in provided formulas
- Document your formula logic

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you clearly explain the difference between IF and IFS?
- [ ] Can you design a business rule using AND + OR together?
- [ ] Can you troubleshoot a formula that returns unexpected results?
- [ ] Can you apply logical functions to a real business problem?

### Documentation Task
Write a brief explanation (300-400 words) of:
- When to use IF vs IFS
- How AND and OR change the logic of your conditions
- One real business scenario where you'd use nested IF

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand IF function syntax and purpose
- [ ] Understand IFS function syntax and when to use it
- [ ] Understand AND function (all conditions must be true)
- [ ] Understand OR function (at least one condition must be true)
- [ ] Know how to combine logical functions
- [ ] Identify common logical formula mistakes

**Hands-On Practice**
- [ ] Created sales classification formula
- [ ] Created employee status formula with AND/OR
- [ ] Built customer segmentation rules
- [ ] Tested formulas with multiple inputs
- [ ] Fixed intentional errors in formulas

**Documentation**
- [ ] Documented your learning in personal notes
- [ ] Explained logic behind each formula created
- [ ] Reflected on applicability to business

---

## 📖 Reference Resources

- Excel IF function syntax and examples
- IFS function vs nested IF comparisons
- AND/OR logic in spreadsheets
- Real business classification examples

---

## 🎯 Next Steps

Tomorrow (Day 2) you'll learn text manipulation functions to clean and parse data. Today's logical functions will be essential when cleaning data conditionally.
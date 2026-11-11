# 📕 Day 3 — Consistency & Referential Integrity

## Learning Objectives
By the end of this day, you should be able to:
- Understand consistency as a data quality dimension
- Identify conflicts and contradictions in data
- Apply referential integrity rules
- Design consistency validation checks
- Diagnose root causes of inconsistency

---

## 📚 Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What is Consistency?**
- **Definition**: Does data remain the same across systems, tables, and time?
- **Questions**:
  - Does the same entity have the same value everywhere?
  - Do related records agree with each other?
  - Do values follow business rules without contradictions?
- **Examples**:
  - Customer name spelled differently in Orders vs Invoices
  - Order total doesn't equal sum of line items
  - Customer status "Active" but last order was 5 years ago
  - Employee department code differs between HR and Finance systems

**Types of Consistency Issues**
- **Within-table consistency**: Contradictions within same table
  - Order quantity is 0 but total is 100
  - Start date after end date
  - Status "Closed" but due date is in future
- **Cross-table consistency**: Same entity inconsistent across tables
  - Customer name: "John Smith" in Customers, "John S." in Orders
  - Product price different in inventory vs sales system
  - Address differs between CRM and Billing
- **Temporal consistency**: Data changes unexpectedly over time
  - Employee salary decreases without explanation
  - Customer location changes every transaction
  - Inventory suddenly has negative count
- **Semantic consistency**: Values don't make business sense
  - Profit = Revenue - Cost, but formula shows different value
  - Customer type "VIP" with $5 lifetime purchases
  - Employee age 12 years old (data entry error, not violation per se, but inconsistent with role)

**Referential Integrity**
- **Definition**: Foreign key relationships must point to existing records
- **Examples**:
  - Invoice's CustomerID must exist in Customers table
  - Order's ProductID must exist in Products table
  - Employee's DepartmentID must exist in Departments table
- **Violations**:
  - "Orphan records": Data points to non-existent parent
  - Deleted parent: Child records left with null or invalid reference
- **Business impact**: Can't join data, can't validate relationships, analytics breaks

**Sources of Inconsistency**
- **Multiple data entry**: Same data entered by different people, different results
- **System integration errors**: Data lost or corrupted during ETL
- **Delayed updates**: One system updated, others not yet synchronized
- **Legacy data conflicts**: Old system rules vs new system rules
- **Manual workarounds**: Users bypassing validation to work around issues
- **Business rule changes**: Old data follows old rules, new data follows new rules

**Business Scenarios**
1. **E-commerce**: Product price must match across website, inventory, and invoicing
2. **Banking**: Account balance must be consistent across all systems
3. **Healthcare**: Patient medical records must be consistent across departments
4. **HR**: Employee salary must match across payroll and accounting systems
5. **Supply Chain**: Inventory counts must be consistent across warehouses

**Consistency Validation Strategies**
- **Relationship validation**: `=COUNTIF(MasterList, ForeignKeyValue) > 0`
- **Cross-table lookup**: `=VLOOKUP(CustomerID, Customers, 1, FALSE)` returns error if not found
- **Calculation check**: `=IF(OrderTotal = SUM(LineItems), "Consistent", "INCONSISTENT")`
- **Business rule check**: `=IF(AND(Status="Closed", DueDate<=TODAY()), "Consistent", "INCONSISTENT")`
- **Comparison across systems**: Export both systems, compare on key fields

**Reconciliation Techniques**
- **Row-by-row reconciliation**: Compare each record in Source A to Source B
- **Summary reconciliation**: Compare totals, counts, sums first
- **Hash value reconciliation**: Create checksum of records, compare hashes
- **Difference reports**: Document every mismatch and root cause

**Key Questions to Explore**
1. Which relationships in your data must be consistent?
2. What business rules define consistency?
3. How would you detect when data becomes inconsistent?
4. What's the business impact of a consistency violation?
5. How do you fix inconsistent data without corrupting relationships?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Identify Consistency Issues**
- Provided dataset: Orders table and Customers table with intentional conflicts
- Tasks:
  - Find customers referenced in Orders that don't exist in Customers
  - Find order totals that don't match sum of line items
  - Find status/date contradictions (e.g., Status="Delivered" but ShipDate > Today)
  - Find duplicate customer records with different names/addresses
  - Document each violation type

**Exercise 2: Build Referential Integrity Checks**
- Create validation formulas:
  - `=IF(COUNTIF(Customers!ID, B2)>0, "Valid Customer", "ORPHAN: Customer not found")`
  - `=IF(COUNTIF(Products!ID, C2)>0, "Valid Product", "ORPHAN: Product not found")`
  - Apply to Orders table to find all orphan records
- Report how many orders reference non-existent customers/products

**Exercise 3: Create Consistency Report**
- Build report showing:
  - Field 1: Source System Data (e.g., Customer name from CRM)
  - Field 2: Destination System Data (e.g., Customer name from Billing)
  - Field 3: Match status: `=IF(A2=B2, "Match", "MISMATCH")`
  - Filter to show only mismatches
  - Categorize mismatches (case difference, abbreviation, spelling)

**Exercise 4: Design Consistency Rules**
- For sample business process, write rules for:
  - Which fields must always have referential integrity
  - Which fields must be identical across systems
  - Which calculated fields must follow formulas
  - What constitutes acceptable vs unacceptable inconsistency
- Apply to provided dataset and identify violations

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain the difference between accuracy and consistency?
- [ ] How would you detect data that's accurate but inconsistent?
- [ ] What's the impact of referential integrity violations?
- [ ] How would you reconcile data from two different systems?

### Documentation Task
Write a brief explanation (300-400 words) covering:
- How consistency differs from accuracy and completeness
- Three specific consistency issues and their business impact
- How you would validate consistency in a multi-table database

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand consistency as a data quality dimension
- [ ] Know types of consistency issues (within-table, cross-table, temporal, semantic)
- [ ] Understand referential integrity and orphan records
- [ ] Know sources of inconsistency
- [ ] Understand consistency validation strategies
- [ ] Know reconciliation techniques

**Hands-On Practice**
- [ ] Identified consistency violations in sample dataset
- [ ] Found orphan records (invalid references)
- [ ] Detected calculation inconsistencies
- [ ] Built referential integrity checks
- [ ] Created cross-system comparison report
- [ ] Applied consistency rules and flagged violations

**Documentation**
- [ ] Documented consistency issues found
- [ ] Explained validation rules applied
- [ ] Reflected on business impact

---

## 📖 Reference Resources

- Data consistency concepts and types
- Referential integrity validation techniques
- Cross-table reconciliation methods
- Business rule validation examples
- Orphan record detection formulas

---

## 🎯 Next Steps

Tomorrow (Day 4) you'll learn about **Validity** — ensuring data conforms to required formats, ranges, and business rules, and learn how to detect invalid data systematically.

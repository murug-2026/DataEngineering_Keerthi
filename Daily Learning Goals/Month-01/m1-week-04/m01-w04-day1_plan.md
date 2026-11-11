# 📘 Day 1 — Lookup Concepts & Relationships Between Datasets

## Learning Objectives
By the end of this day, you should be able to:
- Understand relationship types between datasets
- Identify key fields in data tables
- Design proper data structures for lookups
- Explain data relationships in business context
- Diagnose lookup failures due to relationship issues

---

## 📚 Conceptual Understanding (3 hours)

### Understanding Data Relationships

**What is a Lookup?**
- Matching data from one table to another
- Finding associated information based on a key
- Example: Given customer ID, find customer name
- Foundation of data integration and multi-table analysis

**Why Businesses Need Lookups**
- Separate master data (who/what) from transaction data (what happened)
- Reduce data redundancy
- Maintain single source of truth
- Support efficient data storage
- Enable flexible reporting and analysis

### Types of Relationships

**One-to-One Relationship**
- One record in Table A matches exactly one record in Table B
- Example: Employee → Employee record (each employee has one record)
- Rare in practice; usually indicates denormalization

**One-to-Many Relationship**
- One record in Table A matches multiple records in Table B
- Example: Customer → Sales (one customer can have many sales)
- Most common relationship type in business
- The "One" table is master; "Many" table is transactional

**Many-to-One Relationship**
- Multiple records in Table A match one record in Table B
- Same as One-to-Many, just viewed from opposite direction
- Example: Sales → Customer (many sales point to one customer)

### Master Tables vs Transactional Tables

**Master Tables (Reference/Dimension)**
- Contains unique entities
- Relatively stable (don't change often)
- Examples: Customer master, Product master, Employee master
- Each record represents one unique "thing"

**Transactional Tables (Fact)**
- Contains events/transactions
- Grows continuously
- Examples: Sales transactions, Order lines, Service calls
- May have many records referencing same master record

**Example: Retail Business**
```
Customer Master (One)
├── Customer ID (unique)
├── Customer Name
├── Address
└── Phone

Sales Transaction (Many)
├── Sale ID
├── Customer ID (foreign key)
├── Product ID (foreign key)
├── Sale Date
└── Amount
```

### Key Fields

**Primary Key**
- Field that uniquely identifies each record in a table
- No duplicates allowed
- Example: Customer ID = primary key in Customer Master
- Every record must have a value

**Foreign Key**
- Field in one table that references primary key in another table
- Links related records
- Example: Customer ID in Sales Transaction = foreign key
- Establishes the relationship

**Requirements for Reliable Lookups**
- Primary key must be UNIQUE (no duplicates)
- Primary key must NOT be EMPTY (no blanks)
- Foreign key must match primary key format exactly
- Data types must match (text to text, number to number)
- Keys must be consistent (no typos, extra spaces, case issues)

**What Breaks Lookups**
- Duplicate customer IDs in master table
- Blank customer IDs in either table
- Extra spaces: "CUST-001" vs "CUST-001 "
- Case mismatch: "Smith" vs "smith"
- Data type mismatch: Number 123 vs Text "123"
- Incorrect key: Sales points to non-existent customer ID

### Vertical vs Horizontal Lookups

**Vertical Lookup (Column-based)**
- Data is arranged with records in rows
- Looking down to find matching row
- Then reading across to find desired column
- Most common in business
- Used by VLOOKUP, XLOOKUP, INDEX+MATCH

**Horizontal Lookup (Row-based)**
- Data is arranged with records in columns
- Looking across to find matching column
- Then reading down to find desired row
- Less common in modern databases
- Used by HLOOKUP

### Business Examples of Relationships

**Retail Example**
```
Relationship Chain: Customer → Sales → Product
- Customer Master: Who is the customer?
- Sales Transaction: What did they buy and when?
- Product Master: What is the product?

Lookup Flow:
Sales Record → (lookup) → Customer Name from Customer ID
             → (lookup) → Product Price from Product ID
```

**HR Example**
```
Relationship Chain: Employee → Department → Manager
- Employee Master: Who works here?
- Department Master: Which department?
- Manager Master: Who manages the department?

Lookup Flow:
Employee Record → (lookup) → Department from Dept ID
               → (lookup) → Manager from Manager ID
```

**Order Fulfillment Example**
```
Customer → Order → OrderLine → Product → Supplier
Multiple relationships in one business process
```

### Common Relationship Problems

**Missing Data**
- Product ID in order doesn't exist in Product Master
- Result: VLOOKUP returns #N/A

**Duplicate Keys**
- Two customers with same ID in master
- Result: Lookup returns first match (unpredictable behavior)

**Inconsistent Formatting**
- Sales references "CUST-001" but Master has "cust-001"
- Result: VLOOKUP fails to match

**Wrong Data Types**
- Sales has Customer ID as number (123)
- Master has Customer ID as text ("123")
- Result: Lookup fails due to type mismatch

**Broken Foreign Keys**
- Sales record references customer 999 that doesn't exist
- Result: Lookup error

### Key Questions to Answer

1. How do you identify one-to-many relationships in your business?
2. What makes a good primary key?
3. How do you ensure lookup keys are valid before doing lookup?
4. What would break a lookup in your business data?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercise: Understanding Data Relationships

**Part 1: Build Master Tables (30 minutes)**

**Customer Master Table**
- Create 10-15 sample customers
- Fields: Customer ID, Customer Name, City, Country, Phone
- Make Customer ID unique
- Note: Each customer appears once

**Product Master Table**
- Create 5-10 sample products
- Fields: Product ID, Product Name, Category, Price, Supplier
- Make Product ID unique
- Note: Each product appears once

**Part 2: Build Transaction Table (20 minutes)**

**Sales Transaction Table**
- Create 15-20 sales records
- Fields: Sale ID, Customer ID, Product ID, Sale Date, Quantity, Total
- Customer IDs should reference Customer Master
- Product IDs should reference Product Master
- Note: Same customers/products appear multiple times

**Part 3: Analyze Relationships (20 minutes)**

For the data you created:
- Identify which tables are Master, which are Transactional
- Identify the One side and Many side of relationships
- Identify primary keys and foreign keys
- Document the relationships (write them out)
- Map the lookup flow (which table would lookup from which?)

**Part 4: Find Issues (20 minutes)**

Deliberately introduce data quality issues:
- Add a customer ID to Sales that doesn't exist in Customer Master
- Add a duplicate Customer ID to Customer Master
- Add extra spaces to a Customer ID in one table
- Add a blank Product ID somewhere
- Add a product ID in sales that's formatted differently (text vs number)

Then:
- Identify each issue
- Explain how it would break a lookup
- Suggest how to fix it

**Part 5: Document (10 minutes)**

Create simple data dictionary showing:
- Table name
- Purpose (Master/Transactional)
- Key field
- All field names and purposes
- Relationships to other tables

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you clearly explain customer-product-sales relationships?
- [ ] Can you identify key fields in any dataset?
- [ ] Can you predict what would break a lookup?
- [ ] Can you design proper data structure for lookups?

### Documentation Task
Create a 400-word document titled "Data Relationships in My Business" that includes:
- Main entities in your industry
- Relationships between those entities
- Primary keys and foreign keys
- Real example of how lookups would work
- Potential data quality issues that could break lookups

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand one-to-one, one-to-many relationships
- [ ] Understand Master vs Transactional tables
- [ ] Know what makes a good primary key
- [ ] Know what foreign keys do
- [ ] Understand vertical vs horizontal lookups
- [ ] Identify common lookup failure causes

**Hands-On Practice**
- [ ] Built Customer Master table
- [ ] Built Product Master table
- [ ] Built Sales Transaction table
- [ ] Analyzed relationships between tables
- [ ] Introduced deliberate data quality issues
- [ ] Explained each issue's impact on lookups

**Documentation**
- [ ] Created data dictionary
- [ ] Documented all relationships
- [ ] Explained primary/foreign keys
- [ ] Wrote business relationship analysis

---

## 📖 Reference Resources

- Database relationship types (one-to-many, etc.)
- Master data management concepts
- Primary key and foreign key definitions
- Real business data models

---

## 🎯 Next Steps

Tomorrow (Day 2) you'll learn VLOOKUP and XLOOKUP functions to actually perform lookups based on these relationships. Today's foundation is critical for understanding how lookups work.
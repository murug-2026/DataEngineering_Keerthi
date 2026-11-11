# 📔 Day 5 — Duplicates, Uniqueness & Deduplication

## Learning Objectives
By the end of this day, you should be able to:
- Understand why duplicate records exist and impact on business
- Identify exact duplicates vs fuzzy duplicates (similar but not identical)
- Design deduplication strategies
- Implement Excel techniques to detect and remove duplicates
- Document deduplication decisions and impacts

---

## 📚 Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What is Uniqueness?**
- **Definition**: Each distinct entity appears only once in the dataset
- **Questions**:
  - How many times does each customer appear?
  - Are they exact duplicates or slight variations?
  - Which record should we keep?
- **Impact**: Duplicates skew analysis, overcount revenue/customers, create confusion
- **Difference from completeness/accuracy**: A duplicate record might be complete and accurate, but shouldn't exist

**Types of Duplicates**
- **Exact duplicates**: Every field identical
  - Same customer ID, name, email, phone, address
  - Usually data entry error or system bug
  - Simple to detect and remove
- **Partial/near duplicates**: Same entity, different spelling/variation
  - "John Smith" vs "Jon Smith"
  - "123 Main St" vs "123 Main Street"
  - Name variations from different systems (Jim vs James)
  - Fuzzy match problem
- **Incomplete duplicates**: Same person, some fields differ
  - Customer ID same, but different phone number
  - Might represent legitimate data change or error
- **Cross-system duplicates**: Same entity in different systems
  - Customer in CRM and ERP with different IDs
  - Employee in HR system and Access control system
  - Requires matching logic

**Why Duplicates Occur**
- **User error**: Accidentally entering same record twice
- **System error**: Duplicate on merge, system failure during update
- **Legacy consolidation**: Combining systems without dedup
- **Async updates**: Two users entering same new customer simultaneously
- **Data imports**: Same source data imported multiple times
- **Multiple touches**: Customer contacted, entered separately by different reps
- **No validation**: System allows duplicates instead of preventing them

**Business Impact of Duplicates**
- **Revenue**: $10M revenue counted as $20M if customer appears twice
- **Marketing**: Send duplicate emails, waste marketing budget
- **CRM**: Duplicate customer records confuse staff
- **Analytics**: Statistical analysis shows wrong patterns
- **Operations**: Process each duplicate separately, waste resources
- **Compliance**: Violate regulations requiring unique identifiers
- **Decision-making**: Reports based on duplicated data are wrong

**Business Scenarios**
1. **E-commerce**: Duplicate customer accounts prevent loyalty tracking, shipping confusion
2. **Financial**: Duplicate accounts can trigger false fraud alerts or duplicate charges
3. **CRM**: Sales team doesn't know duplicate accounts exist, gives poor service
4. **Inventory**: Duplicate SKUs cause system confusion, wrong stock levels
5. **Healthcare**: Duplicate patient records dangerous—medical history scattered

**Deduplication Strategies**

**Strategy 1: Exact Duplicate Removal**
- Simple approach: Delete records identical in all fields
- Formula: Mark first occurrence as "Keep", others as "Delete"
- Risk: Low, since no ambiguity about which to keep
- Excel: Remove Duplicates, Advanced Filter unique records

**Strategy 2: Fuzzy Matching**
- Match similar records (not exact)
- Methods:
  - Name soundex matching: "Smith" = "Smythe"
  - Edit distance: "John" vs "Jon" = 1 character difference
  - Exact field matching: Same phone number = probably same person
- Excel limitations: Advanced formulas needed, not built-in
- Better: Specialized tools (Fuzzy Lookup in Excel add-in)

**Strategy 3: Business Key Matching**
- Deduplicate on unique business identifier
- Examples:
  - Customer by email address (emails are unique)
  - Employee by SSN (SSNs are unique)
  - Product by SKU (SKUs are unique)
- Most reliable for known business keys
- Excel: `=COUNTIF($A$1:$A$100, A1)` counts occurrences by business key

**Strategy 4: Master Data Management (MDM)**
- Create single source of truth
- All systems reference master record
- Prevents duplicates from being created
- Long-term solution, requires governance

**Handling Duplicates Decision Process**
1. **Identify**: Which records are duplicates? (exact, fuzzy, or by business key)
2. **Prioritize**: Which duplicate to keep? (most recent, most complete, from trusted source)
3. **Merge**: Should we combine data from duplicates? (e.g., keep all addresses/phones)
4. **Link**: Should we maintain relationship record (this was merged with that)?
5. **Delete**: Remove duplicate records
6. **Audit**: Track what was deleted and why
7. **Communicate**: Inform users of changes made

**Entity Resolution**
- Complex problem: Matching same entity across different sources
- Examples: Customer in 3 different systems with different IDs
- Methods:
  - Manual review: Expert looks at candidates, matches by hand
  - Rule-based: Apply matching rules in sequence
  - Probabilistic: Scoring approach, potential matches with confidence
- Excel limitations: Limited capability for complex entity resolution

**Key Questions to Explore**
1. What makes a record a "duplicate" in your business?
2. How do you decide which duplicate to keep?
3. What's the cost of keeping duplicates vs accidentally removing real data?
4. How would you handle fuzzy duplicates?
5. How do you prevent duplicates going forward?

---

## 💻 Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Identify Exact Duplicates**
- Provided dataset: Customer records with intentional duplicates
- Tasks:
  - Find exact duplicate records (all fields identical)
  - Mark first occurrence as "Keep", others as "Delete"
  - Count total duplicates found
  - Calculate impact if kept (e.g., revenue count)
  - Document which records are duplicates

**Exercise 2: Build Duplicate Detection Formulas**
- Create formulas to find:
  - Exact duplicates: `=COUNTIF($A$2:$A$1000, A2)` (if >1, it's duplicate)
  - Business key duplicates: `=COUNTIF($Email$2:$Email$1000, Email2)` (count by email)
  - Near duplicates: Use EXACT or manual review for similar names
  - All occurrence flags: `=IF(COUNTIF($A$2:A2, A2)=1, "First", "Duplicate")`

**Exercise 3: Develop Deduplication Rules**
- For sample customer dataset, create rules:
  - Which field(s) determine uniqueness? (CustomerID? Email? SSN?)
  - When duplicates exist, how do you decide which to keep?
    - Keep most recent record?
    - Keep most complete record?
    - Keep from most trusted source?
  - Do you merge data from duplicates or just delete?
  - How do you handle near-duplicates (same person, slightly different name)?
- Document decision for each rule

**Exercise 4: Remove and Document**
- Apply deduplication to dataset:
  - Use Excel Remove Duplicates function or formulas
  - Document what was removed (count, examples, reason)
  - Create before/after comparison
  - Verify correct records kept (spot-check)
  - Document impact (revenue change, customer count change)
  - Create audit trail showing what was deleted and why

---

## 🤔 Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Can you explain why duplicate handling is critical for data quality?
- [ ] What's the difference between exact and fuzzy duplicates?
- [ ] How would you design deduplication for your business?
- [ ] What's the risk of overly aggressive deduplication?

### Documentation Task
Write a comprehensive deduplication plan (400-500 words) covering:
- How you would identify duplicates in a specific business scenario
- Decision criteria for which duplicate to keep
- How you would handle fuzzy/near-duplicates
- How you would prevent duplicates going forward

---

## ✅ Daily Checklist

**Conceptual Understanding**
- [ ] Understand uniqueness and duplicate detection
- [ ] Know types of duplicates (exact, partial, incomplete, cross-system)
- [ ] Understand why duplicates occur
- [ ] Know business impact of duplicates
- [ ] Understand deduplication strategies (exact removal, fuzzy matching, business key, MDM)
- [ ] Know entity resolution basics

**Hands-On Practice**
- [ ] Identified exact duplicates in sample dataset
- [ ] Created duplicate detection formulas
- [ ] Developed deduplication rules for business scenario
- [ ] Applied deduplication logic to data
- [ ] Compared before/after results
- [ ] Documented all deduplication decisions

**Documentation**
- [ ] Created comprehensive deduplication plan
- [ ] Documented rules for handling edge cases
- [ ] Explained business impact of deduplication

---

## 📖 Reference Resources

- Duplicate detection techniques and patterns
- Excel duplicate removal methods
- Fuzzy matching concepts
- Business key identification
- Entity resolution strategies
- Deduplication audit trail management
- MDM principles

---

## 🎯 Next Steps

This completes Week 5: Data Quality Fundamentals (Accuracy, Completeness, Consistency, Validity, Uniqueness). 

Next week (Week 6) you'll dive into **Data Quality Advanced** topics including data profiling, business rule validation, exception handling, and quality metrics to measure and report data quality systematically.

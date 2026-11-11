# ?? Day 1 — Data Profiling & Statistical Analysis

## Learning Objectives
By the end of this day, you should be able to:
- Master data profiling techniques and methodologies
- Apply statistical analysis to data quality assessment
- Identify distribution patterns and statistical anomalies
- Design profiling-based validation rules
- Create comprehensive profiling reports

---

## ?? Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What is Data Profiling?**
- Systematic examination and analysis of data characteristics
- Discovers data patterns, distributions, and anomalies
- Bridges gap between validation (checking rules) and exploration
- Creates foundation for quality rules and thresholds
- Business impact: Prevents issues before they cause problems

**Statistical Foundations**
- **Descriptive statistics**: Measures that describe data distribution
  - Central tendency: Mean, median, mode
  - Spread: Variance, standard deviation, range, IQR
  - Shape: Skewness, kurtosis
- **Inferential statistics**: Draw conclusions about population from sample
- **Correlation analysis**: Relationships between variables
- **Trend analysis**: Patterns over time

**Why Data Profiling Matters**
- Reveals hidden data quality issues validation alone misses
- Establishes baselines for normal vs. anomalous data
- Informs risk assessment and business decisions
- Supports data governance and policy development
- Enables better predictive models and analytics

**Distribution Analysis**
- **Normal distribution**: Bell-shaped curve, symmetric
  - 68% within 1 std dev, 95% within 2 std dev, 99.7% within 3
  - Used to establish outlier thresholds
- **Skewed distribution**: Long tail on one side
  - Right-skewed (positive): Tail extends right (e.g., income)
  - Left-skewed (negative): Tail extends left (e.g., exam scores)
- **Bimodal/multimodal**: Multiple peaks indicate mixed populations
- **Uniform distribution**: All values equally likely

**Outlier Detection Methods**
- **Statistical method**: Values > mean ± (3 × std dev) or > Q3 + (1.5 × IQR)
- **Percentage method**: Top/bottom X% of values
- **Predictive method**: Values don't fit model
- **Domain method**: Business rules define outliers

**Business Scenarios**
1. **Retail Company**: Sales amount profiling shows most orders -500, but 2% are +. Investigation finds wholesale accounts—requires different handling
2. **Customer Database**: Age profiling shows bimodal (peaks at 25 and 55)—likely represents two customer segments
3. **Financial Services**: Account balance follows right-skewed distribution—top 10% of customers hold 70% of assets
4. **Supply Chain**: Inventory count profiling shows frequent values ending in 5 or 0—suggests rounding, needs verification
5. **Manufacturing**: Quality measurement shows unexpected high variability—signals equipment calibration issue

**Profiling Workflow**
1. Collect profiling metrics for each field
2. Analyze distributions and patterns
3. Identify outliers and anomalies
4. Investigate root causes
5. Document findings and recommendations
6. Create rules based on profiling insights

**Key Questions to Explore**
1. What would a normal distribution of customer ages look like?
2. How would you know if your data is abnormal?
3. What causes data to be skewed or have multiple distributions?
4. When is an outlier a data error vs. a valid anomaly?
5. How would you use profiling to prevent quality issues?

---

## ?? Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Statistical Analysis**
- Download sample dataset (sales, customer, or financial data)
- Calculate for a numeric field (amount, age, revenue):
  - Mean: =AVERAGE(Data)
  - Median: =MEDIAN(Data)
  - Mode: =MODE.SNGL(Data)
  - Std Dev: =STDEV.S(Data)
  - Min/Max: =MIN(Data), =MAX(Data)
  - Quartiles: =QUARTILE.INC(Data, 1) through =QUARTILE.INC(Data, 3)
- Create summary statistics table
- Interpret what each statistic reveals

**Exercise 2: Distribution Analysis**
- Create histogram of values
- Observe distribution shape (normal, skewed, bimodal)
- Calculate skewness: =SKEW(Data) (positive = right-skewed, negative = left-skewed)
- Identify whether distribution is symmetric
- Document distribution characteristics and implications

**Exercise 3: Outlier Detection**
- Identify statistical outliers using z-score:
  - Formula: =ABS((Value - AVERAGE(Data))/STDEV.S(Data))
  - Outlier if > 3 (99.7% confidence)
- Or use IQR method:
  - Q1 = =QUARTILE.INC(Data, 1)
  - Q3 = =QUARTILE.INC(Data, 3)
  - IQR = Q3 - Q1
  - Outlier if Value < Q1 - (1.5 × IQR) or Value > Q3 + (1.5 × IQR)
- Create outlier report with count, percentage, examples
- Classify each outlier (error, domain anomaly, business anomaly)

**Exercise 4: Profiling-Based Validation Rules**
- Create rule based on profiling insights:
  - Acceptance range: Mean ± (2 × Std Dev)
  - Formula: =IF(AND(Value >= Mean-2*StdDev, Value <= Mean+2*StdDev), "Within range", "OUTLIER")
- Apply to dataset
- Document normal range, expected outlier percentage, investigation triggers
- Create alert rules for extreme values

---

## ?? Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] How does data profiling differ from simple validation?
- [ ] What would a business person learn from a distribution histogram?
- [ ] How would you explain a z-score to a non-technical stakeholder?
- [ ] When should you investigate an outlier vs. adjust rules?
- [ ] How does profiling support data governance?

### Documentation Task
Write detailed explanation (400-500 words) covering:
- How data profiling builds on concepts from Week 5
- Statistical methods you would use for quality assessment
- Business scenario where profiling revealed important issues
- How to communicate statistical findings to non-technical audiences

---

## ? Daily Checklist

**Conceptual Understanding**
- [ ] Understand purpose and value of data profiling
- [ ] Know key statistical measures (mean, median, std dev, quartiles, skewness)
- [ ] Understand distribution types and what they reveal
- [ ] Know multiple outlier detection methods (statistical, IQR, domain)
- [ ] Understand difference between statistical anomalies and data errors
- [ ] Know how profiling informs validation rules

**Hands-On Practice**
- [ ] Calculated complete statistical summary for dataset
- [ ] Created and interpreted distribution histogram
- [ ] Detected outliers using multiple methods
- [ ] Calculated z-scores and IQR bounds
- [ ] Designed profiling-based validation rules
- [ ] Created outlier classification and investigation plan

**Documentation**
- [ ] Documented statistical findings clearly
- [ ] Explained distribution characteristics
- [ ] Justified validation thresholds with profiling data
- [ ] Communicated findings appropriately for audience

---

## ?? Reference Resources

- Statistical analysis fundamentals
- Outlier detection methods (z-score, IQR, Tukey's)
- Distribution types and characteristics (normal, skewed, bimodal)
- Excel statistical functions reference
- Data profiling best practices and frameworks
- Case studies: Profiling discoveries and their impact

---

## ?? Next Steps

Tomorrow (Day 2) you'll learn **Business Rule Validation** — combining multiple quality dimensions to create complex rules that enforce business logic and requirements.

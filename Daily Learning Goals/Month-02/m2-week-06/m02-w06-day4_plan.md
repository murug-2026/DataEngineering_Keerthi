# ?? Day 4 — Quality Metrics & KPIs

## Learning Objectives
By the end of this day, you should be able to:
- Define meaningful data quality metrics and KPIs
- Calculate accuracy, completeness, and other quality scores
- Track quality trends and improvements
- Present quality metrics to stakeholders
- Use metrics to drive quality improvements

---

## ?? Conceptual Understanding (3 hours)

### Core Concepts to Learn

**What are Quality Metrics?**
- Measurable indicators of data quality status
- Bridge between technical issues and business impact
- Enable objective assessment and comparison
- Track trends and improvements over time
- Drive accountability and prioritization

**Key Quality Metrics**
1. **Accuracy Score**: % of records with correct values
   - Formula: (Total records - Inaccurate records) / Total records × 100%
   - Target: 95-99%
2. **Completeness Score**: % of required fields populated
   - Formula: (Fields with data / Total required fields) × 100%
   - Target: 99%+
3. **Consistency Score**: % of records aligned with business rules
   - Formula: (Consistent records / Total records) × 100%
   - Target: 98%+
4. **Validity Score**: % of records passing validation rules
   - Formula: (Valid records / Total records) × 100%
   - Target: 99%+
5. **Uniqueness Score**: % of records without duplicates
   - Formula: (Unique records / Total records) × 100%
   - Target: 100%

**Composite Quality Scores**
- Overall Quality Score: Average of all dimension scores
- Weighted Quality Score: Different dimensions weighted by importance
  - Example: Accuracy 40%, Completeness 30%, Consistency 20%, Validity 10%
  - Score = (0.4 × Accuracy) + (0.3 × Completeness) + (0.2 × Consistency) + (0.1 × Validity)

**Business KPIs from Quality Data**
- **Data timeliness**: Time from capture to availability
- **Exception rate**: % of records requiring manual intervention
- **Rework rate**: % of records failing initial validation
- **Data recovery cost**: Cost to fix data quality issues
- **Compliance rate**: % of audit checks passed
- **Customer impact**: Complaints/issues from data problems

**Quality Trend Analysis**
- Track metrics over time (daily, weekly, monthly)
- Identify improving vs. degrading dimensions
- Correlate with process changes or events
- Calculate improvement rate (velocity)
- Project future state if trends continue

**Benchmarking and Targets**
- **Industry benchmarks**: Typical quality scores by industry
- **Best practice targets**: What excellent organizations achieve
- **Organizational targets**: Based on strategy and capabilities
- **Progressive targets**: Improve incrementally
- **Realistic vs. aspirational**: Balance improvement with operational reality

**Quality Reporting**
- **Executive dashboard**: High-level overall quality score
- **Detailed reports**: Quality by dimension, data source, business area
- **Trend charts**: Historical quality changes
- **Exception lists**: Top issues needing resolution
- **Root cause analysis**: Why metrics are at current level

**Business Scenarios**
1. **Retail**: Track accuracy of product pricing. Target 99.5%. Current 97.2%. Root cause: manual price updates. Solution: automate price feed. Expect 99.5% within 2 weeks
2. **Healthcare**: Completeness of patient allergies. Target 100%. Current 85%. Issue: legacy data gaps. Action: recovery program targeting high-risk gaps first
3. **Financial**: Consistency of account balances. Target 99.9%. Current 98.5%. Problem: integration lag between systems. Fix: reduce batch timing
4. **HR**: Validity of employee records. Target 100%. Current 95%. Issue: incomplete hire data. Action: change process to collect upfront
5. **Supply Chain**: Uniqueness of SKU data. Target 100%. Current 97%. Problem: duplicates from multiple imports. Solution: master data consolidation

**Communicating Metrics to Stakeholders**
- Non-technical audiences: Use percentages and dashboards
- Technical audiences: Include formulas and calculation details
- Business leaders: Emphasize impact and ROI of improvements
- Operations teams: Focus on trends and root causes
- Executives: Highlight strategic implications

**Key Questions to Explore**
1. What quality metrics matter most for your business?
2. What's a good vs. bad quality score?
3. How do you balance perfection with practicality?
4. What causes quality scores to fluctuate?
5. How do quality metrics drive business decisions?

---

## ?? Hands-On Practice (2 hours)

### Practice Exercises

**Exercise 1: Calculate Quality Scores**
- Given dataset with known issues (inaccurate, incomplete, inconsistent, invalid, duplicate records)
- Calculate individual dimension scores:
  - Count inaccurate records and calculate accuracy score
  - Count incomplete records and calculate completeness score
  - Count inconsistent records and calculate consistency score
  - Count invalid records and calculate validity score
  - Count duplicate records and calculate uniqueness score
- Document calculation method and findings

**Exercise 2: Create Weighted Quality Score**
- Determine weights based on business importance:
  - Accuracy: 40% (critical for financial decisions)
  - Completeness: 30% (needed for customer service)
  - Consistency: 20% (important for analytics)
  - Validity: 10% (caught by validation)
- Calculate: Score = (Accuracy × 0.4) + (Completeness × 0.3) + (Consistency × 0.2) + (Validity × 0.1)
- Interpret what score means (e.g., 96.5% = "Good but needs attention")

**Exercise 3: Track Quality Trends**
- Collect quality scores over time (simulate with daily data for 1 month)
- Create trend chart showing scores over time
- Calculate improvement rate: (Latest - Oldest) / Number of periods
- Identify which dimensions are improving vs. degrading
- Project forward: If trend continues, what will score be in 3 months?

**Exercise 4: Create Quality Dashboard**
- Design visual dashboard showing:
  - Overall quality score (gauge or percentage)
  - Quality by dimension (bar chart)
  - Trend over time (line chart)
  - Top issues (list with count)
  - Status vs. target (bullet chart)
- Include key statistics and insights
- Make suitable for different audiences (executive summary)

---

## ?? Reflection & Consolidation (1 hour)

### Reflection Questions

- [ ] Why is measuring quality more important than just fixing issues?
- [ ] How do quality metrics align with business goals?
- [ ] What's the relationship between quality metrics and data value?
- [ ] How would you use metrics to convince management to invest in quality?

### Documentation Task
Write detailed explanation (400-500 words) covering:
- How to select quality metrics that matter for your business
- Connection between technical metrics and business outcomes
- Dashboard design for different audiences
- How metrics drive continuous improvement

---

## ? Daily Checklist

**Conceptual Understanding**
- [ ] Understand key quality metrics and how to calculate them
- [ ] Know how to create weighted composite scores
- [ ] Understand trend analysis and projections
- [ ] Know benchmarking and target-setting principles
- [ ] Understand quality reporting for different audiences
- [ ] Know how metrics align with business strategy

**Hands-On Practice**
- [ ] Calculated all five quality dimension scores
- [ ] Created weighted composite score
- [ ] Tracked quality trends over time
- [ ] Calculated improvement rates and projections
- [ ] Created quality dashboard with visualizations
- [ ] Communicated findings to different audiences

**Documentation**
- [ ] Documented calculation methods
- [ ] Explained metric significance
- [ ] Interpreted trends and patterns
- [ ] Connected metrics to business decisions

---

## ?? Reference Resources

- Quality metric definitions and formulas
- Benchmarking data by industry
- Best practices for metric selection
- Dashboard design principles
- Trend analysis and forecasting
- Case studies: Quality improvement through metrics

---

## ?? Next Steps

Tomorrow (Day 5) you'll learn **Data Quality Governance** — establishing organizational structures, policies, and accountability for maintaining data quality.

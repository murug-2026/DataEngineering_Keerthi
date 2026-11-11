# Excel Learning Diary – Data Types, Tables and Formatting

**Date:** 11 November 2026

### Q1. What are Excel's data types?

**Answer:**

Data types define the kind of information stored in an Excel cell. Common data types include:

- Text – Names and words.
- Number – Numerical values.
- Date – Calendar dates.
- Time – Time values.
- Currency – Monetary values.
- Percentage – Percentage values.
- Boolean – TRUE or FALSE.
- Error – Formula errors such as #VALUE! and #DIV/0!.

### Q2. How does Excel internally store dates (serial numbers)?

**Answer:**

Excel stores dates as serial numbers rather than ordinary text.

- 1 January 1900 is serial number 1.
- Each following day increases the serial number by 1.
- Time is stored as a decimal portion of a number.
- For example, 12:00 PM is represented as 0.5.

This allows Excel to perform date calculations easily.

### Q3. What is the difference between data type and format?

**Answer:**

- Data Type defines what kind of information is stored in a cell.
- Format determines how the information is displayed.

Example: A value of 5000 can be displayed as ₹5,000.00 using currency formatting without changing its underlying numerical value.

### Q4. What are common formatting options in Excel?

**Answer:**

Common formatting options include:

- Font formatting – Change font style, size and colour.
- Number formatting – Display numbers, currency and percentages.
- Alignment – Align text horizontally and vertically.
- Borders – Add borders around cells.
- Fill Colour – Apply background colours.
- Text Wrapping – Display long text across multiple lines.
- Merge & Centre – Combine cells and centre content.
- Conditional Formatting – Highlight cells based on conditions.
- Cell Styles – Apply predefined formatting styles.

### Q5. What is an Excel Table?

**Answer:**

An Excel Table is a structured range of data organised into rows and columns with built-in features.

- Each column has a heading.
- Each row represents a record.
- Tables automatically expand when new data is added.
- They provide built-in sorting and filtering options.

### Q6. How do tables improve filtering, sorting and formulas?

**Answer:**

- Filtering helps display specific records based on conditions.
- Sorting arranges data alphabetically, numerically or by date.
- Formulas automatically extend to new rows in calculated columns.
- New records are included when the table expands.

### Q7. What is structured referencing?

**Answer:**

Structured referencing is a method of referring to table columns using their names instead of traditional cell references.

Example:

Traditional formula:
`=B2*C2`

Structured reference:
`=[@Quantity]*[@Price]`

It makes formulas easier to understand and maintain.

### Q8. What are Named Ranges?

**Answer:**

Named Ranges allow users to assign meaningful names to individual cells or groups of cells instead of using cell addresses.

Example: Instead of referring to cell B2, we can name it `Sales_Amount`.

**Uses:**
- Makes formulas easier to read.
- Simplifies calculations.
- Reduces confusion when working with large datasets.
- Makes formulas easier to maintain.

### Q9. How do you create and manage Named Ranges?

**Answer:**

**Creating a Named Range:**
1. Select a cell or range of cells.
2. Go to the Formulas tab.
3. Click Define Name.
4. Enter a meaningful name.
5. Click OK.

**Managing Named Ranges:**
- Open the Formulas tab.
- Select Name Manager.
- View, edit or delete existing names.
- Change the cell references associated with a name.

**Shortcut:** Ctrl + F3 opens Name Manager.

### Q10. What is the difference between Table Name, Column Name and Named Range?

**Answer:**

- Table Name: Identifies an entire Excel Table. Example: `Sales`.
- Column Name: Identifies a particular column within a table. Example: `Product`.
- Named Range: Assigns a custom name to a cell or group of cells. Example: `Tax_Rate`.

### Q11. What formatting mistakes cause formula errors?

**Answer:**

**1. Numbers Stored as Text**
- Excel treats numerical values as text.
- Mathematical calculations may not work correctly.
- Solution: Convert the values into numbers.

**2. Dates Stored as Text**
- Excel does not recognise the values as actual dates.
- Date calculations and sorting may produce incorrect results.
- Solution: Convert text into recognised Excel dates using DATEVALUE or Text to Columns.

**3. Inconsistent Formats**
- Different formats within the same column create confusion.
- Example: Mixing numerical values, currency symbols and text.
- Solution: Apply consistent formatting throughout the dataset.

### Q12. Why is consistent formatting critical for business datasets?

**Answer:**

Consistent formatting ensures that business data is accurate, organised and easy to analyse.

- Improves data accuracy.
- Makes sorting, filtering and calculations easier.
- Maintains data quality.
- Improves the readability of reports and dashboards.
- Supports automation using formulas and Power Query.
- Helps businesses make reliable, data-driven decisions.

**Example:** Using a consistent DD-MM-YYYY date format and currency format throughout a sales dataset.

 
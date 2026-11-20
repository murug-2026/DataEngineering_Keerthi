# Data Quality – Questions and Answers

## 1. What are the critical data quality issues for your industry?

**Answer:**

Data quality issues vary depending on the industry, but some common critical issues affect almost every industry, including IT, healthcare, banking, retail, and manufacturing.

The major data quality issues are:

1. **Missing Data:** Important information is missing from records, such as customer names, phone numbers, addresses, or transaction details.
2. **Duplicate Data:** The same customer, employee, or transaction is recorded multiple times, leading to inaccurate reports.
3. **Inconsistent Data:** Data is stored in different formats. For example, dates may be recorded as `DD-MM-YYYY` in one record and `MM-DD-YYYY` in another.
4. **Inaccurate Data:** Incorrect information is entered into the system, such as wrong phone numbers, email addresses, or sales figures.
5. **Outdated Data:** Information is no longer current, such as old customer addresses or outdated employee records.
6. **Invalid Data:** Data does not follow the expected rules or format, such as a 10-digit phone number containing only 8 digits.
7. **Lack of Standardization:** Different departments use different naming conventions, units, or formats.
8. **Data Integrity Issues:** Relationships between datasets are incorrect, such as sales transactions linked to non-existent customer IDs.

**Conclusion:**

Maintaining good data quality is essential for accurate reporting, better decision-making, efficient operations, and reliable business analysis.

---

## 2. How would you systematically clean a large messy dataset?

**Answer:**

To systematically clean a large messy dataset, I would follow a step-by-step data cleaning process to identify and correct errors while maintaining data accuracy and consistency.

### Steps involved in cleaning a large dataset

1. **Understand the Dataset:** Examine the dataset to understand its structure, columns, data types, and purpose.
2. **Identify Missing Values:** Check for blank cells or missing information. Decide whether to fill them with appropriate values or remove records when necessary.
3. **Remove Duplicate Records:** Identify and remove duplicate entries using Excel's Remove Duplicates feature or the `UNIQUE()` function.
4. **Correct Inconsistent Formatting:** Standardize text, dates, numbers, and other formats using functions such as:
   - `TRIM()` – Removes unnecessary spaces.
   - `CLEAN()` – Removes non-printable characters.
   - `UPPER()` – Converts text to uppercase.
   - `LOWER()` – Converts text to lowercase.
   - `PROPER()` – Capitalizes the first letter of each word.
   - `SUBSTITUTE()` – Replaces specific characters or text.
5. **Validate Data:** Apply data validation rules to identify incorrect entries, such as invalid email addresses, incorrect phone numbers, or negative quantities.
6. **Correct Data Types:** Ensure that dates are stored as dates, numerical values as numbers, and text values as text.
7. **Identify Outliers and Errors:** Use sorting, filtering, conditional formatting, and statistical methods to identify unusual or suspicious values.
8. **Standardize Categories:** Ensure consistent naming conventions. For example, replace variations such as "Bangalore", "Bengaluru", and "BANGALORE" with one standard value.
9. **Verify Data Quality:** Recheck the cleaned dataset to ensure that missing values, duplicates, inconsistencies, and errors have been handled correctly.
10. **Document the Changes:** Maintain a record of the cleaning steps performed so that the process can be repeated and audited.

### Excel Functions and Features Used

| Function / Feature | Purpose |
|---|---|
| `TRIM()` | Remove extra spaces |
| `CLEAN()` | Remove non-printable characters |
| `SUBSTITUTE()` | Replace unwanted text |
| `IFERROR()` | Handle formula errors |
| `COUNTIF()` | Identify duplicates |
| `ISBLANK()` | Identify empty cells |
| `LEN()` | Validate text length |
| Remove Duplicates | Remove duplicate records |
| Conditional Formatting | Highlight errors and inconsistencies |
| Data Validation | Restrict invalid entries |

**Conclusion:**

Data cleaning should follow a systematic process rather than randomly correcting individual cells. The goal is to make the dataset accurate, consistent, complete, and reliable for further analysis.

---

## 3. What would your data dictionary look like for your business?

**Answer:**

A **data dictionary** is a document that describes the structure of a dataset, including column names, data types, definitions, allowed values, and validation rules.

For a retail business, I would create a data dictionary to ensure that everyone understands the meaning and format of each field in the dataset.

### Example: Data Dictionary for a Retail Business

| Column Name | Data Type | Description | Validation Rules |
|---|---|---|---|
| Customer_ID | Text | Unique customer identification number | Must be unique and not blank |
| Customer_Name | Text | Full name of the customer | Cannot be blank |
| Email | Text | Customer's email address | Must follow valid email format |
| Phone_Number | Text | Customer's contact number | Must contain 10 digits |
| City | Text | Customer's residential city | Must follow standard city names |
| Order_ID | Text | Unique order identification number | Must be unique |
| Order_Date | Date | Date when the order was placed | Must be a valid date |
| Product_ID | Text | Unique product identification number | Must exist in product records |
| Product_Name | Text | Name of the purchased product | Cannot be blank |
| Quantity | Whole Number | Number of units purchased | Must be greater than zero |
| Unit_Price | Decimal | Price of one product | Must be zero or greater |
| Total_Amount | Decimal | Total value of the order | Quantity × Unit Price |
| Payment_Status | Text | Current payment status | Paid, Pending, Failed |
| Order_Status | Text | Current order status | Delivered, Pending, Cancelled |

### What should a good data dictionary contain?

1. **Column Name:** Name of the field in the dataset.
2. **Data Type:** Whether the field contains text, numbers, dates, etc.
3. **Description:** Explains what the field represents.
4. **Allowed Values:** Specifies acceptable values for categorical fields.
5. **Validation Rules:** Defines the conditions that data must satisfy.
6. **Example Values:** Provides sample entries for better understanding.

### Why is a data dictionary important?

- Maintains consistency across datasets.
- Helps identify incorrect or invalid entries.
- Makes data easier to understand and analyze.
- Improves communication between departments.
- Establishes clear data entry standards.
- Simplifies data cleaning and validation.

**Conclusion:**

A data dictionary acts as a reference guide for a business dataset. It ensures that everyone follows the same definitions, formats, and validation rules, improving overall data quality and reliability.

---

## 4. How do you validate that cleaned data is correct?

**Answer:**

After cleaning a dataset, I would validate it by performing a series of checks to ensure that the data is accurate, complete, consistent, and reliable.

### Steps to validate cleaned data

1. **Check for Missing Values:** Verify that important fields do not contain unexpected blank cells. Use Excel's `ISBLANK()` function to identify missing values.
2. **Check for Duplicate Records:** Ensure that duplicate entries have been removed using Excel's Remove Duplicates feature or `COUNTIF()` function.
3. **Validate Data Formats:** Check whether dates, numbers, phone numbers, and email addresses follow the expected formats.
4. **Verify Data Accuracy:** Compare the cleaned data against the original source or trusted records to ensure that no incorrect changes were introduced.
5. **Check Data Consistency:** Ensure that similar values follow the same naming conventions. For example, all city names should use a standard format.
6. **Apply Validation Rules:** Verify that values meet predefined business rules, such as phone numbers containing exactly 10 digits and product quantities being greater than zero.
7. **Check Logical Relationships:** Ensure that related values make sense. For example, Total Amount should equal Quantity multiplied by Unit Price.
8. **Compare Before and After Cleaning:** Compare the number of records, duplicates, missing values, and errors before and after cleaning.
9. **Perform Spot Checks:** Manually inspect a sample of cleaned records to identify any remaining errors.

### Excel Functions and Features Used

| Function / Feature | Purpose |
|---|---|
| `ISBLANK()` | Identify missing values |
| `COUNTIF()` | Identify duplicates |
| `IF()` | Apply logical validation rules |
| `LEN()` | Check text length |
| `ISNUMBER()` | Check whether a value is numeric |
| `IFERROR()` | Identify or handle formula errors |
| Conditional Formatting | Highlight suspicious values |
| Data Validation | Restrict invalid entries |
| Pivot Tables | Identify inconsistencies and unusual patterns |

### Example

Suppose a retail dataset contains the following information:

| Customer | Phone Number | Quantity | Unit Price |
|---|---|---|---|
| Rahul | 9876543210 | 2 | 500 |
| Priya | 12345678 | 3 | 200 |
| Amit | 9876543210 | -1 | 300 |

During validation, we can identify:

- Priya's phone number is invalid because it contains only 8 digits.
- Amit's phone number is a duplicate.
- Amit's quantity is invalid because it is negative.

**Conclusion:**

Data validation ensures that the cleaning process has not introduced new errors and that the final dataset meets the required quality standards. Cleaned data should always be checked before using it for reporting, analysis, or business decision-making.

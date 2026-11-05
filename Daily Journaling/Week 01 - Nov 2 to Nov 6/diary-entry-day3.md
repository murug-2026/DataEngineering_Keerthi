# DATABASE FUNDAMENTALS

## 1. What is a row in a database table?

- A row is a horizontal record in a database table.
- It contains related values across multiple columns.
- Each row represents one person, object or event.
- Rows are also called records or tuples.
- Example: One row can contain all the details of one student.

## 2. Why is a row also called a record?

- A row stores a complete set of information about one entity.
- Its values are organised across different columns.
- Together, these values describe one particular entity.
- A primary key can uniquely identify the record.
- Example: A student's ID, name and age form one record.

## 3. What does a record represent in real life?

- A record represents one real-world entity or event.
- In a student database, it can represent one student.
- In banking, it can represent one transaction.
- In e-commerce, it can represent one customer order.
- It stores the related details of that entity or event.

## 4. How do rows differ from columns in terms of meaning?

- Rows represent individual records or entities.
- Columns represent attributes or properties of those entities.
- A row contains values across multiple columns.
- A column stores the same type of information for many records.
- Rows are horizontal, while columns are vertical.

##5. Can two rows be identical? What happens if they are?

- Yes, a database may allow identical rows if uniqueness is not
  enforced.
- Duplicate records can cause confusion and inaccurate analysis.
- A primary key gives each record a unique identifier.
- If a duplicate primary-key value is inserted, the database rejects
  it.
- Unique constraints can also prevent duplicates in selected columns.

## 6. What is a column in a database table?

- A column is a vertical structure in a database table.
- It stores one specific type of information or attribute.
- Examples include ID, name, age and department.
- Each column has a name and an assigned data type.
- Columns are also called fields or attributes.

## 7. Why is a column also called a field?

- A column is called a field because it represents one information
  category.
- It stores a particular attribute for each record.
- Examples include student name, age and department.
- A field has a name and usually a defined data type.
- Each row contains a value for that field.

## 8. What does a field represent in real life?

- A field represents one specific detail about an entity or event.
- In a student database, it can be the student's name or age.
- In banking, it can be a transaction amount or date.
- In an employee database, it can be salary or designation.
- A field stores one particular attribute in a record.

## 9. How do columns define the structure of a table?

- Columns specify what information a table will store.
- Each column represents an attribute, such as ID, name or age.
- Column names identify the information being stored.
- Data types define the kind of values each column can contain.
- Together, columns establish the structure of every record.

## 10. What is the difference between a field name and a field value?

- A field name identifies the type of information stored in a column.
- A field value is the actual data stored for a particular record.
- Field names remain the same across records.
- Field values can differ from one row to another.
- Example: Name is the field name; Arun is a field value.

## 11. What are data types in databases?

- Data types define the kind of data a column can store.
- Common types include integer, decimal, text, date and Boolean.
- They help databases validate and process information correctly.
- Each column is assigned a suitable data type.
- Example: An Age column may use the INTEGER data type.

## 12. Why do we need data types instead of storing everything as text?

- Data types ensure values are stored in suitable forms.
- Numeric types allow calculations without extra text conversion.
- They help prevent invalid values from being entered.
- Suitable types improve data processing and storage efficiency.
- They also make sorting, filtering and analysis more reliable.

## 13. What are the most common data types?

- Integer: Stores whole numbers, such as 21 or 100.
- Float/Decimal: Stores decimal numbers, such as 99.50.
- Text/String: Stores characters and words, such as Arun.
- Date/Time: Stores dates and times, such as 2026-11-05.
- Boolean: Stores logical values, either TRUE or FALSE.

## 14. What happens if you store wrong data in a column?

- The database may reject a value that does not match the column's
  type.
- Invalid text in a numeric field can cause a conversion error.
- Incorrect data can reduce consistency and accuracy.
- It may prevent calculations or produce unreliable results.
- Example: Entering Twenty in an INTEGER Age column may cause an error.

## 15. How do data types help in validation and efficient storage?

- Validation: Data types check that values match the expected
  type.
- They help prevent invalid entries, such as text in a numeric field.
- Efficient storage: They use suitable storage formats for
  different values.
- Appropriate types can reduce unnecessary storage and improve
  processing.
- Example: Store age as an INTEGER rather than as text.

## 16. What is the difference between data type and data format?

- A data type defines what kind of value a column can store.
- A data format defines how a value is represented or displayed.
- Data types include INTEGER, VARCHAR and DATE.
- Formats include DD-MM-YYYY and YYYY-MM-DD.
- In simple terms, type is the kind of data; format is its representation.

## 17. What are examples of formats for dates, times, currency and phone numbers?

- Date: 05-11-2026 (DD-MM-YYYY), 11/05/2026 (MM/DD/YYYY),
  2026-11-05 (ISO date).
- Time: 14:30 (24-hour) or 02:30 PM (12-hour).
- Currency: ₹1,500.00 (Indian Rupee), $100.00 (US Dollar),
  €85.00 (Euro).
- Phone: +91-9876543210 or 09876543210.
- These formats represent information in different, standardised ways.

## 18. Why do formats matter in data consistency?

- Formats ensure information is represented uniformly.
- Consistent formats reduce confusion between different
  representations.
- They make data easier to compare, sort and filter.
- Standard formats help combine information from multiple sources.
- They support more reliable reporting and analysis.

## 19. What problems occur if formats are inconsistent across systems?

- Different date formats can cause interpretation errors.
- Inconsistent formats make combining data from systems difficult.
- Number and currency differences can cause calculation problems.
- The same information may be mistaken for duplicate records.
- These issues can affect reporting and data analysis.

## 20. How do you convert data from one format to another?

- Data conversion changes information into another format or data
  type.
- Excel can change date, time, number and currency display formats.
- SQL uses functions such as CAST() and CONVERT() for type
  conversion.
- Python uses functions such as int(), float() and
  pd.to_datetime().
- Example: 05-11-2026 can be converted to 2026-11-05.
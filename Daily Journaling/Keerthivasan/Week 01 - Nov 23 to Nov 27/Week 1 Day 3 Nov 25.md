**Rows and Records**

**1. What is a row in a database table?**

A row is one horizontal entry in a table that holds all the data about a single item. If a table is a grid, each row is one line across it, with one value for each column.

**2. Why is a row also called a record?**

The two terms come from different traditions. "Row" is the visual, table-based term used in relational database theory and SQL. "Record" comes from older file-based systems, where data was stored as a sequence of records, like entries in a card catalog. In a database table, they mean the same thing: one complete set of related facts about one thing.

**3. What does a record represent in real life?**

It represents one real-world entity or event. For example:

|Table|Representation|
|---|---|
|Students	|One student|
|Transactions	|One purchase or payment|

So a row in a Students table might be: (101, "Akshitaa", "Biotechnology", 2026). That single row is everything the database knows about student 101.

**4. How do rows differ from columns?**

**Columns** define what kind of information is stored (the attribute or field): student_id, name, department. Every value in a column has the same data type and meaning.
**Rows** hold the actual data for one specific item, with one value per column.

Simple Way to remember Column Represents "what" And Row instances "Who and which one". Column changes the Design of the table. Adding row only adds more data to the table.

**5. Can two rows be identical? What happens if they are?**

In theory, Relation Dataset is a set, So duplicate rows aren't allowed. In SQL tables will allow identical rows unless you prevent them.

When duplicates exist:

- You can't tell them apart, so updating or deleting that one row can accidentally affect both.
- Counts, sums, and averages become wrong (e.g., one transaction counted twice).
- Relationships to other tables become Unclear

To Prevent this each Cell has an Primary Key which can be used for rejecting duplicates. So, every row can be easily identifiable even if any duplicates are present

**Columns and Fields**


**1. What is a column in a database table?**

A column is one vertical slice of a table that holds a single type of information for every item in the table.

In a Students table, name is a column: it contains the name of every student, one per row.

**2. Why is a column also called a field?**

"Column" is the table-based term used in SQL and relational theory, while "field" comes from the older file and form-based tradition, where each record was made up of named fields, like the blanks on a paper form.

**3. What does a field represent in real life?**

It represents one property or attribute of the real-world thing the table describes.

**4. How do columns define the structure of a table?**

The set of columns is the table's blueprint (its **schema**).

Each column specifies:

- **A name:** Such as student_id.
- **A data type:** Such as integer, text, date, or decimal.
- **Constraints:** Such as NOT NULL, UNIQUE, or PRIMARY KEY, which control what values are allowed.

Every row must follow this blueprint: it gets exactly one value for each column, of the declared type.

Adding, removing, or changing a column changes the structure itself, while rows just fill that structure with data.

**Data Types**

**1. What are data types in databases?**

A data type is a rule attached to a column that says what kind of value it can hold: a whole number, a piece of text, a date, and so on. It is part of the column's definition, alongside its name, so every value in that column must fit the declared type.

**2. Why do we need data types instead of storing everything as text?**

Storing everything as a text would be convinient, but it breaks the one the thing why data are supposed to be stored  and used

- Most data would work as a guessing thing instead of providing the information
- No real Calculation 
- Wrong Comparisions and sorting
- It takes up more storage and queries as a text.

**3. What are the most common data types?**

1. Integer
2. Float/Decimal
3. Text/String
4. Boolean (True/False)
5. Date/Time

**4. What happens if you store wrong data in a column (e.g., text in a numeric field)?**
- Rejected with an error
- Altered/Automatically Converted or Truncated

**5. How do data types help in validation and efficient storage?** 

The database acts as a gatekeeper, rejecting values that don't match the type (letters in a number field, 31-02-2026 in a date field).
Combined with constraints such as NOT NULL, CHECK (age >= 0), or UNIQUE, types keep the data clean at the source rather than relying on every application to check it.

Each type has a specified storage bytes for example Int takes about Four bytes
and SmallINT takes about 2-4 bytes. 
Choosing the smallest storage bytes increases the Speed and lowers storage.

**Data Formats**

**1. What is the difference between data type and data format?**

Data type is what kind of value a column holds (integer, date, text). It is a rule enforced by the database and decides how the value is stored and what operations are allowed.
Data format is how a value is written or displayed (e.g., 25-11-2026 vs 11/25/2026). It is a presentation or representation convention.

**2. What are examples of formats for:
Date (DD-MM-YYYY, MM/DD/YYYY, ISO 8601)
Time (24-hour vs 12-hour)
Currency (₹, $, €)
Phone numbers (+91-9876543210 vs 09876543210)**

|Category|Format|Example|
|---|---|---|
|Date| DD-MM-YYYY|07-03-2005|
||MM/DD/YYYY| 03/07/2005|
||ISO 8601| 2005-03-07|
|Time|24 Hours|19:30|
||12 Hour|7:30|
|Currency|₹, $, €|₹100, $1, €0.85|
|Phone numbers|International (E.164)|+91-9876543210|
||With separators|+91-9876543210|
||National|09876543210|

**3. Why do formats matter in data consistency?**

Consistent formats mean every value of a field can be compared, sorted, searched, grouped, and validated the same way.

**4. What problems occur if formats are inconsistent across systems?**

- Misinterpretation
- Wrong sorting and filtering
- Duplicates and failed matches
- Calculation errors
- Time zone and clock confusion

**5. How do you convert data from one format to another?**

The general approach is to Parse them and format using SQL or Python





# Excel Text Cleaning Functions 

## 1. When would you use each cleaning function?

Excel provides several text functions to clean and standardise data:

- **TRIM()** – Removes extra spaces from text, leaving only single spaces between words.
  - Example: `=TRIM(A2)`
  - Use it when data contains unwanted leading, trailing, or repeated spaces.

- **CLEAN()** – Removes non-printable characters from text.
  - Example: `=CLEAN(A2)`
  - Use it when imported data contains hidden characters.

- **UPPER()** – Converts all letters to uppercase.
  - Example: `=UPPER(A2)`
  - Use it when standardising text to uppercase.

- **LOWER()** – Converts all letters to lowercase.
  - Example: `=LOWER(A2)`
  - Use it when standardising email addresses or text to lowercase.

- **PROPER()** – Capitalises the first letter of each word.
  - Example: `=PROPER(A2)`
  - Use it to standardise people's names and titles.

- **SUBSTITUTE()** – Replaces specific characters or text with other text.
  - Example: `=SUBSTITUTE(A2,"-","")`
  - Use it to remove or replace unwanted symbols and characters.

## 2. What's the correct order to combine multiple cleaning functions?

A useful general order is:

1. **CLEAN()** – Remove non-printable characters.
2. **TRIM()** – Remove extra spaces.
3. **SUBSTITUTE()** – Replace or remove specific unwanted characters.
4. **UPPER(), LOWER(), or PROPER()** – Apply the required letter case.

Example:

```excel
=PROPER(TRIM(CLEAN(A2)))
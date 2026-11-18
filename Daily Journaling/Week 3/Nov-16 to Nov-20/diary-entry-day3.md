# Excel Text Functions 

## 1. How do you extract the first 5 characters of a product code?

**Answer:**

Use the `LEFT()` function to extract a specified number of characters from the beginning of a text string.

**Syntax:**
```excel
=LEFT(text, num_chars)
```

**Example:**

If cell `A2` contains `PRD12345`:

```excel
=LEFT(A2,5)
```

**Result:** `PRD12`

---

## 2. How would you extract the middle portion of an ID?

**Answer:**

Use the `MID()` function to extract characters from a text string, starting at a specified position.

**Syntax:**
```excel
=MID(text, start_num, num_chars)
```

**Example:**

If cell `A2` contains `ABC123XYZ`:

```excel
=MID(A2,4,3)
```

**Result:** `123`

---

## 3. What's the difference between using MID vs LEFT/RIGHT?

**Answer:**

- `LEFT()` extracts characters from the beginning of a text string.
- `RIGHT()` extracts characters from the end of a text string.
- `MID()` extracts characters from a specified position within a text string.

**Example:**

If `A2` contains `ABC123XYZ`:

| Function | Formula | Result |
|---|---|---|
| LEFT | `=LEFT(A2,3)` | ABC |
| RIGHT | `=RIGHT(A2,3)` | XYZ |
| MID | `=MID(A2,4,3)` | 123 |

---

## 4. When would you use each cleaning function?

**Answer:**

Excel text-cleaning functions help remove unwanted spaces and characters, replace text, and standardize data.

| Function | When to use it | Example |
|---|---|---|
| `TRIM()` | Removes leading and trailing spaces and reduces repeated spaces between words to single spaces. | `=TRIM(A2)` |
| `CLEAN()` | Removes non-printing characters from text. | `=CLEAN(A2)` |
| `SUBSTITUTE()` | Replaces specific text or characters wherever they occur. | `=SUBSTITUTE(A2,"&"," ")` |
| `REPLACE()` | Replaces characters based on their position in the text. | `=REPLACE(A2,4,3,"999")` |
| `UPPER()` | Converts all letters to uppercase. | `=UPPER(A2)` |
| `LOWER()` | Converts all letters to lowercase. | `=LOWER(A2)` |
| `PROPER()` | Capitalizes the first letter of each word. | `=PROPER(A2)` |
| `TEXT()` | Converts a number to text in a specified format. | `=TEXT(A2,"₹#,##0")` |

### Combining Cleaning Functions

**Example:**

```excel
=PROPER(TRIM(CLEAN(A2)))
```

This formula:
1. `CLEAN()` removes non-printing characters.
2. `TRIM()` removes unnecessary spaces.
3. `PROPER()` capitalizes the first letter of each word.

**Remember:** `TRIM()` and `CLEAN()` are especially useful when preparing raw datasets for data analysis, reporting and dashboard creation.

# Excel Text Functions 

### Q1. How do you extract the first 5 characters of a product code?

**Answer:**

Use the `LEFT` function in Excel to extract characters from the beginning of a text string.

**Syntax:**
```excel
=LEFT(text, num_chars)
```

**Example:**
```excel
=LEFT(A2,5)
```

If A2 contains `PROD12345`, the result will be `PROD1`.

**Business Use Case:** Extracting product prefixes, country codes, or starting characters from product IDs.

---

### Q2. How would you extract the middle portion of an ID?

**Answer:**

Use the `MID` function to extract characters from a specific position within a text string.

**Syntax:**
```excel
=MID(text, start_num, num_chars)
```

**Example:**
```excel
=MID(A2,4,3)
```

If A2 contains `EMP12345`, the result will be `123`.

**Explanation:**
- `A2` – Cell containing the ID.
- `4` – Starting position.
- `3` – Number of characters to extract.

**Business Use Case:** Extracting employee numbers, department codes, or region codes from IDs.

---

### Q3. What's the difference between using MID vs LEFT/RIGHT?

**Answer:**

The main difference is the position from which each function extracts characters.

| Function | Purpose | Extraction |
|---|---|---|
| LEFT | Extracts characters from the beginning | Left side |
| RIGHT | Extracts characters from the end | Right side |
| MID | Extracts characters from a specific position | Any position |

**Example:**

Suppose A2 contains `EMP12345`.

```excel
=LEFT(A2,3)     Result: EMP
=RIGHT(A2,3)    Result: 345
=MID(A2,4,3)    Result: 123
```

**When to Use:**
- LEFT: Extracting product prefixes.
- RIGHT: Extracting the last few digits of an ID.
- MID: Extracting specific characters from the middle.

**Key Takeaway:** LEFT extracts from the beginning, RIGHT extracts from the end, and MID extracts from a specified position.

---

### Q4. How do you validate that text has the expected length?

**Answer:**

Use the `LEN` function to count the total number of characters in a text string.

**Syntax:**
```excel
=LEN(text)
```

**Example:**

Suppose product codes must contain exactly 8 characters.

| Product Code | Formula | Result |
|---|---|---|
| PROD1234 | `=LEN(A2)` | 8 |
| ELEC567 | `=LEN(A3)` | 7 |
| MOBI12345 | `=LEN(A4)` | 9 |

**Validate Using IF:**

```excel
=IF(LEN(A2)=8,"Valid","Invalid")
```

**Explanation:**
- `LEN(A2)` counts the characters.
- `=8` checks whether the length is exactly 8.
- `"Valid"` is returned if the condition is TRUE.
- `"Invalid"` is returned if the condition is FALSE.

**Business Use Case:**
- Validating product codes.
- Checking employee ID lengths.
- Verifying phone number lengths.
- Identifying incomplete or incorrectly formatted data.



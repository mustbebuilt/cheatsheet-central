## Excel for Software Engineers — Cheat Sheet

### 1. Basic cell calculations

| Task       | Formula        | Example          |
| ---------- | -------------- | ---------------- |
| Add        | `=A2+B2`       | Add two values   |
| Subtract   | `=A2-B2`       | Difference       |
| Multiply   | `=A2*B2`       | Quantity × price |
| Divide     | `=A2/B2`       | Percentage/rate  |
| Percentage | `=A2/B2*100`   | Convert to %     |
| Round      | `=ROUND(A2,2)` | 2 decimal places |

### 2. Common functions

| Function  | Example                       | Purpose               |
| --------- | ----------------------------- | --------------------- |
| `SUM`     | `=SUM(B2:B10)`                | Total                 |
| `AVERAGE` | `=AVERAGE(B2:B10)`            | Arithmetic mean       |
| `MIN`     | `=MIN(B2:B10)`                | Smallest value        |
| `MAX`     | `=MAX(B2:B10)`                | Largest value         |
| `COUNT`   | `=COUNT(B2:B10)`              | Count numeric values  |
| `COUNTA`  | `=COUNTA(B2:B10)`             | Count non-empty cells |
| `COUNTIF` | `=COUNTIF(B2:B10,">=50")`     | Count matching values |
| `SUMIF`   | `=SUMIF(A2:A10,"Web",B2:B10)` | Conditional total     |
| `IF`      | `=IF(B2>=50,"Pass","Fail")`   | Conditional value     |

genui{"learning_viz":{"type_id":"ARITHMETIC_MEAN","initial_values":{"observation1":72,"observation2":65,"observation3":83},"locale_override":"en-GB"}}

### 3. Combining fields

**Concatenate text:**

```excel
=CONCAT(A2," ",B2)
```

Produces:

```text
Aisha Khan
```

Alternative:

```excel
=A2&" "&B2
```

---

## 4. Making Excel database-ready

Think of an Excel row as a **database record** and a column as a **database field**.

### Good

| student_id | first_name | last_name | mark |
| ---------- | ---------- | --------- | ---: |
| STU-001    | Aisha      | Khan      |   72 |
| STU-002    | Ben        | Smith     |   55 |

### Avoid

- Merged cells
- Multiple values in one field
- Decorative headings above the data
- Empty rows
- Formulas where you need fixed values
- Currency symbols embedded in numeric data
- Inconsistent dates
- Inconsistent spelling/capitalisation

### Think about data types

```text
student_id    → VARCHAR
first_name    → VARCHAR
mark          → INTEGER
average       → DECIMAL
date_joined   → DATE
passed        → BOOLEAN
```

---

## 6. CSV — the database-friendly format

CSV is often the simplest bridge between Excel and a database.

```text
student_id,first_name,last_name,mark
STU-001,Aisha,Khan,72
STU-002,Ben,Smith,55
```

In Excel:

**File → Save As → CSV UTF-8**

> **Use UTF-8 CSV** where possible, particularly when names or text may contain non-English characters.

---

## 7. CSV import considerations

Before importing into MySQL/PostgreSQL/etc., check:

- Does the first row contain column names?
- Are columns in the correct order?
- Are numbers actually numbers?
- Are dates consistently formatted?
- Are empty fields intended to be `NULL`?
- Are primary keys unique?
- Are there duplicate records?
- Do text fields contain commas?
- Is the file encoded as UTF-8?

---

## 8. Useful text-cleaning functions

| Function     | Example                   | Purpose              |
| ------------ | ------------------------- | -------------------- |
| `TRIM`       | `=TRIM(A2)`               | Remove extra spaces  |
| `UPPER`      | `=UPPER(A2)`              | Convert to uppercase |
| `LOWER`      | `=LOWER(A2)`              | Convert to lowercase |
| `PROPER`     | `=PROPER(A2)`             | Capitalise words     |
| `LEFT`       | `=LEFT(A2,3)`             | First 3 characters   |
| `RIGHT`      | `=RIGHT(A2,4)`            | Last 4 characters    |
| `LEN`        | `=LEN(A2)`                | String length        |
| `SUBSTITUTE` | `=SUBSTITUTE(A2," ","_")` | Replace text         |

Example — create a database-friendly username:

```excel
=LOWER(CONCAT(A2,".",B2))
```

Produces:

```text
aisha.khan
```

---

## 9. A simple software-engineering workflow

```text
Raw data
   ↓
Clean
   ↓
Validate
   ↓
Calculate
   ↓
Generate IDs
   ↓
Check duplicates
   ↓
Export CSV
   ↓
Import into database
```

### Practical exercise

Create a student summary table with one row per student and these columns:

- `studentID`
- `first_name`
- `last_name`
- `task_1`, `task_2`, `task_3`
- `total_marks`
- `average_mark`
- `passed`
- `full_name`

Suggested workflow:

1. Add a `studentID` column using:

```excel
="STU-"&TEXT(ROW()-1,"000")
```

2. Add the task scores in separate columns, e.g. `C2:E2` for task marks.

3. Calculate the total for each student:

```excel
=SUM(C2:E2)
```

4. Calculate the average mark:

```excel
=AVERAGE(C2:E2)
```

5. Decide whether the student passed a threshold such as 40%:

```excel
=IF((AVERAGE(C2:E2)/100)>=0.4,"Pass","Fail")
```

6. Concatenate the full name:

```excel
=A2&" "&B2
```

7. Format the `average_mark` column as a percentage or number with one or two decimal places.

8. Save the finished sheet as a CSV for database import:

**File → Save As → CSV UTF-8**

This creates a file like:

```text
studentID,first_name,last_name,task_1,task_2,task_3,total_marks,average_mark,passed,full_name
STU-001,Aisha,Khan,72,65,83,220,73.33%,Pass,Aisha Khan
STU-002,Ben,Smith,35,42,39,116,38.67%,Fail,Ben Smith
```

Example output:

| studentID | first_name | last_name | task_1 | task_2 | task_3 | total_marks | average_mark | passed | full_name |
| --------- | ---------- | --------- | ------ | ------ | ------ | ----------- | ------------ | ------ | --------- |
| STU-001   | Aisha      | Khan      | 72     | 65     | 83     | 220         | 73.33%       | Pass   | Aisha Khan |
| STU-002   | Ben        | Smith     | 35     | 42     | 39     | 116         | 38.67%       | Fail   | Ben Smith |

This is a good beginner exercise because it combines basic arithmetic, average calculations, conditional logic, and text concatenation in a realistic student-record example.



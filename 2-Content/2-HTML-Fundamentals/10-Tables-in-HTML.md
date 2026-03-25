# Day 10 — Tables in HTML

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 2 — HTML Fundamentals
🧪 **Lab Experiments:** 5, 6

---

## Learning Objectives

By the end of this session, students will be able to:
- Create tables using `<table>`, `<tr>`, `<th>`, `<td>`
- Apply table attributes (border, cellpadding, cellspacing, colspan, rowspan)
- Use tables for displaying data (timetable, layouts)
- Understand when to use and NOT use tables

---

## 1. Basic Table Structure

```html
<table border="1">
    <tr>                    <!-- Table Row -->
        <th>Name</th>       <!-- Table Header (bold, centered) -->
        <th>Age</th>
    </tr>
    <tr>
        <td>Rahul</td>     <!-- Table Data (regular cell) -->
        <td>20</td>
    </tr>
    <tr>
        <td>Priya</td>
        <td>21</td>
    </tr>
</table>
```

**Renders as:**

| Name | Age |
|------|-----|
| Rahul | 20 |
| Priya | 21 |

### Key Tags

| Tag | Purpose |
|-----|---------|
| `<table>` | Creates the table container |
| `<tr>` | Table Row |
| `<th>` | Table Header (bold + centered) |
| `<td>` | Table Data (regular cell) |
| `<caption>` | Table title/caption |
| `<thead>` | Groups header rows |
| `<tbody>` | Groups body rows |
| `<tfoot>` | Groups footer rows |

---

## 2. Table Attributes

```html
<table border="2" cellpadding="10" cellspacing="5" width="80%" bgcolor="#f0f0f0">
    <caption><b>Student Details</b></caption>
    <tr bgcolor="#333333">
        <th><font color="white">Name</font></th>
        <th><font color="white">Roll No</font></th>
        <th><font color="white">Course</font></th>
    </tr>
    <tr>
        <td align="center">Amit Kumar</td>
        <td align="center">001</td>
        <td align="center">BCA</td>
    </tr>
</table>
```

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `border` | Border thickness (pixels) | `border="1"` |
| `cellpadding` | Space inside cells (between content and border) | `cellpadding="10"` |
| `cellspacing` | Space between cells | `cellspacing="5"` |
| `width` | Table width (px or %) | `width="80%"` |
| `height` | Table height | `height="300"` |
| `bgcolor` | Background color | `bgcolor="#f0f0f0"` |
| `align` | Table alignment | `align="center"` |

### Cell Attributes

| Attribute | Purpose | Applied To |
|-----------|---------|-----------|
| `colspan` | Span multiple columns | `<td>` or `<th>` |
| `rowspan` | Span multiple rows | `<td>` or `<th>` |
| `align` | Horizontal alignment | `<td>` or `<th>` |
| `valign` | Vertical alignment | `<td>` or `<th>` |

---

## 3. Colspan & Rowspan

### Colspan (Merge Columns)

```html
<table border="1" cellpadding="8">
    <tr>
        <th colspan="3">Student Information</th>
    </tr>
    <tr>
        <th>Name</th>
        <th>Roll No</th>
        <th>Grade</th>
    </tr>
    <tr>
        <td>Rahul</td>
        <td>001</td>
        <td>A</td>
    </tr>
</table>
```

### Rowspan (Merge Rows)

```html
<table border="1" cellpadding="8">
    <tr>
        <th>Day</th>
        <th>Subject</th>
    </tr>
    <tr>
        <td rowspan="2">Monday</td>
        <td>Web Technology</td>
    </tr>
    <tr>
        <td>Data Structures</td>
    </tr>
</table>
```

---

## Practical Session

### 🧪 Lab Experiment 5: Class Timetable

**Objective:** Create a table to show your class timetable.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BCA II Semester - Class Timetable</title>
</head>
<body>

    <h1 align="center">BCA II Semester — Class Timetable</h1>
    <h3 align="center">Mandsaur University | Academic Year 2025-26</h3>

    <table border="1" cellpadding="10" cellspacing="0" width="90%" align="center">
        <caption><strong>Weekly Schedule</strong></caption>
        
        <!-- Header Row -->
        <tr bgcolor="#1565C0">
            <th><font color="white">Time / Day</font></th>
            <th><font color="white">Monday</font></th>
            <th><font color="white">Tuesday</font></th>
            <th><font color="white">Wednesday</font></th>
            <th><font color="white">Thursday</font></th>
            <th><font color="white">Friday</font></th>
            <th><font color="white">Saturday</font></th>
        </tr>
        
        <!-- Period 1 -->
        <tr>
            <td bgcolor="#E3F2FD" align="center"><strong>9:00 - 10:00</strong></td>
            <td align="center">Web Technology</td>
            <td align="center">Data Structures</td>
            <td align="center">Web Technology</td>
            <td align="center">Mathematics</td>
            <td align="center">Data Structures</td>
            <td align="center">Mathematics</td>
        </tr>
        
        <!-- Period 2 -->
        <tr>
            <td bgcolor="#E3F2FD" align="center"><strong>10:00 - 11:00</strong></td>
            <td align="center">Mathematics</td>
            <td align="center">Web Technology</td>
            <td align="center">Data Structures</td>
            <td align="center">Web Technology</td>
            <td align="center">Mathematics</td>
            <td align="center">Library</td>
        </tr>
        
        <!-- Break -->
        <tr bgcolor="#FFF9C4">
            <td align="center"><strong>11:00 - 11:30</strong></td>
            <td colspan="6" align="center"><em>☕ Tea Break</em></td>
        </tr>
        
        <!-- Period 3-4 (Lab) -->
        <tr>
            <td bgcolor="#E3F2FD" align="center"><strong>11:30 - 1:30</strong></td>
            <td colspan="2" align="center" bgcolor="#E8F5E9">
                <strong>Web Technology Lab</strong><br>(Mon-Tue)
            </td>
            <td colspan="2" align="center" bgcolor="#FFF3E0">
                <strong>DS Lab</strong><br>(Wed-Thu)
            </td>
            <td colspan="2" align="center" bgcolor="#F3E5F5">
                <strong>Math Tutorial</strong><br>(Fri-Sat)
            </td>
        </tr>
        
        <!-- Lunch -->
        <tr bgcolor="#FFECB3">
            <td align="center"><strong>1:30 - 2:30</strong></td>
            <td colspan="6" align="center"><em>🍽️ Lunch Break</em></td>
        </tr>
        
        <!-- Period 5 -->
        <tr>
            <td bgcolor="#E3F2FD" align="center"><strong>2:30 - 3:30</strong></td>
            <td align="center">English</td>
            <td align="center">EVS</td>
            <td align="center">English</td>
            <td align="center">EVS</td>
            <td align="center">Sports</td>
            <td align="center">—</td>
        </tr>
    </table>

</body>
</html>
```

---

### 🧪 Lab Experiment 6: University Infrastructure Page (Table Layout)

**Objective:** Use tables to provide a layout for a university infrastructure page.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>University Infrastructure</title>
</head>
<body bgcolor="#FAFAFA">

    <!-- Header using table -->
    <table width="100%" bgcolor="#0D47A1" cellpadding="15">
        <tr>
            <td width="20%" align="center">
                <img src="https://via.placeholder.com/80x80?text=MU" alt="Logo">
            </td>
            <td>
                <font color="white" size="6"><b>Mandsaur University</b></font><br>
                <font color="#BBDEFB" size="3">Excellence in Education</font>
            </td>
        </tr>
    </table>

    <!-- Navigation using table -->
    <table width="100%" bgcolor="#1565C0" cellpadding="8">
        <tr>
            <td align="center"><a href="#"><font color="white">Home</font></a></td>
            <td align="center"><a href="#"><font color="white">About</font></a></td>
            <td align="center"><a href="#"><font color="white">Departments</font></a></td>
            <td align="center"><a href="#"><font color="white">Facilities</font></a></td>
            <td align="center"><a href="#"><font color="white">Contact</font></a></td>
        </tr>
    </table>

    <!-- Content area using 2-column table -->
    <table width="90%" align="center" cellpadding="15" cellspacing="10">
        <tr>
            <!-- Left column: Image -->
            <td width="50%" valign="top">
                <img src="https://via.placeholder.com/400x300?text=Computer+Lab" 
                     alt="Computer Lab" width="100%">
                <p align="center"><b>State-of-the-Art Computer Labs</b></p>
            </td>
            <!-- Right column: Description -->
            <td width="50%" valign="top">
                <h2>Computer Labs</h2>
                <p>
                    Our computer labs are equipped with the latest hardware and 
                    software. Each lab has 60 workstations with high-speed internet.
                </p>
                <p>
                    <b>Software:</b> VS Code, MySQL, Python, Java, etc.<br>
                    <b>Operating Systems:</b> Windows 11, Ubuntu Linux<br>
                    <b>Internet:</b> 100 Mbps dedicated line
                </p>
            </td>
        </tr>
        <tr>
            <td width="50%" valign="top">
                <h2>Library</h2>
                <p>
                    The central library houses over 50,000 books and subscribes 
                    to leading journals and e-resources.
                </p>
            </td>
            <td width="50%" valign="top">
                <img src="https://via.placeholder.com/400x300?text=Library" 
                     alt="Library" width="100%">
                <p align="center"><b>Central Library</b></p>
            </td>
        </tr>
    </table>

    <!-- Footer -->
    <table width="100%" bgcolor="#0D47A1" cellpadding="10">
        <tr>
            <td align="center">
                <font color="white">&copy; 2026 Mandsaur University | All Rights Reserved</font>
            </td>
        </tr>
    </table>

</body>
</html>
```

---

## Practice Exercise

Create a table showing the **marks of 5 students** in 4 subjects with:
- Student names in the first column
- Subject names as column headers
- Use `colspan` for a merged title row
- Use `rowspan` for merging cells where appropriate
- Calculate total marks in the last column
- Use different background colors for header, even/odd rows
- Add a `<caption>`

---

## Summary

| Tag/Attribute | Purpose |
|--------------|---------|
| `<table>` | Container for the table |
| `<tr>` | Table row |
| `<th>` | Header cell (bold, centered) |
| `<td>` | Data cell |
| `border` | Border width |
| `cellpadding` | Inner space in cells |
| `cellspacing` | Space between cells |
| `colspan` | Merge columns |
| `rowspan` | Merge rows |
| `bgcolor` | Background color |

---

*Day 10 of 55 | Unit 2 — HTML Fundamentals | Web Technology (25BCA060)*

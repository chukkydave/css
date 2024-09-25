---

### **HTML Tables Overview**

HTML tables allow you to organize data in rows and columns. They are useful for displaying structured information, such as schedules, data reports, or comparison charts.

A basic HTML table consists of multiple elements:

1. `<table>`: Defines the overall table.
2. `<tr>` (Table Row): Defines a row in the table.
3. `<th>` (Table Header): Defines a header cell in the table (usually bold and centered by default).
4. `<td>` (Table Data): Defines a standard data cell.

---

### **Beginner Concepts**

#### **1. Basic Table Structure**

A simple table with two rows and two columns:

```html
<table>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
  <tr>
    <td>Row 2, Cell 1</td>
    <td>Row 2, Cell 2</td>
  </tr>
</table>
```

- `<th>` is used for table headers (usually at the top or left).
- `<td>` is used for regular table cells.

---

#### **2. Adding a Table Caption**

A caption gives your table a title. It’s optional but can help with clarity.

```html
<table>
  <caption>My Table Caption</caption>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
</table>
```

---

#### **3. Adding Borders to Tables**

By default, tables don’t have borders. You can add borders to cells and the table itself with CSS:

```html
<table border="1">
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
</table>
```

You can use CSS to style tables more flexibly, such as setting thicker borders or spacing between cells.

---

### **Intermediate Concepts**

#### **1. Colspan and Rowspan**

Sometimes you want a cell to span multiple columns or rows.

- **`colspan`**: Makes a cell span across multiple columns.
- **`rowspan`**: Makes a cell span across multiple rows.

Example:

```html
<table border="1">
  <tr>
    <th colspan="2">Header Spanning 2 Columns</th>
  </tr>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
  <tr>
    <td rowspan="2">Cell Spanning 2 Rows</td>
    <td>Row 2, Cell 2</td>
  </tr>
  <tr>
    <td>Row 3, Cell 2</td>
  </tr>
</table>
```

---

#### **2. Table Head, Body, and Footer**

To structure a table, you can group rows into three sections:

- **`<thead>`**: Table head (usually for the header row).
- **`<tbody>`**: Table body (the main content).
- **`<tfoot>`**: Table footer (for summary information).

Example:

```html
<table border="1">
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row 1, Cell 1</td>
      <td>Row 1, Cell 2</td>
    </tr>
    <tr>
      <td>Row 2, Cell 1</td>
      <td>Row 2, Cell 2</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Footer Cell 1</td>
      <td>Footer Cell 2</td>
    </tr>
  </tfoot>
</table>
```

---

### **Advanced Concepts**

#### **1. Table Styling with CSS**

You can fully customize tables with CSS to improve their readability and design.

- **Border-collapse**: This property makes sure the borders of cells and the table are combined, reducing space between cells.

```html
<style>
  table {
    border-collapse: collapse;
    width: 100%;
  }

  th, td {
    border: 1px solid black;
    padding: 8px;
    text-align: left;
  }

  th {
    background-color: #f2f2f2;
  }
</style>

<table>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
</table>
```

---

#### **2. Zebra Striping**

Adding alternating row colors improves the readability of large tables.

```html
<style>
  tr:nth-child(even) {
    background-color: #f2f2f2;
  }
</style>

<table border="1">
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
  <tr>
    <td>Row 2, Cell 1</td>
    <td>Row 2, Cell 2</td>
  </tr>
</table>
```

---

### **Exercises**

1. **Beginner Exercise: Simple Table Creation**
   - Create a table with three rows and three columns. The first row should be headers. Add data in the remaining rows and experiment with borders.

2. **Intermediate Exercise: Colspan and Rowspan**
   - Create a table where the first header spans across two columns. Add a cell in the table that spans two rows. Practice combining `colspan` and `rowspan`.

3. **Advanced Exercise: Styling a Table**
   - Create a table and use CSS to:
     - Collapse borders.
     - Add padding to cells.
     - Add zebra striping to alternate rows.
     - Change the background color of the header.

---

### **Classwork Instruction**

**Create a Product Price List Using Tables**

1. Create a table with the following columns:
   - Product Name
   - Product Description
   - Price
2. Add 5 products, filling in the appropriate details.
3. Style the table by:
   - Adding borders to all cells.
   - Giving the header a different background color.
   - Alternating row colors for better readability.

---

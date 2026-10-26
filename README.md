# 📊 Functional Programming Spreadsheet

A browser-based **spreadsheet application built with HTML, CSS, and JavaScript**.

The project recreates core spreadsheet behavior by dynamically generating cells, evaluating formulas, resolving cell references and ranges, and supporting custom spreadsheet functions.

The main purpose of this project was to practice **functional programming concepts, array methods, recursion, regular expressions, higher-order functions, DOM manipulation, and expression parsing** in JavaScript.

## ✨ Features

The spreadsheet includes:

- Dynamically generated spreadsheet cells
- Columns `A` through `J`
- Rows `1` through `99`
- Direct cell references such as `A1`
- Cell ranges such as `A1:B5`
- Arithmetic expressions
- Operator precedence
- Spreadsheet-style functions
- Automatic formula evaluation when a cell changes
- Basic circular self-reference protection

## 🧠 How It Works

The spreadsheet interface is generated dynamically with JavaScript rather than manually creating hundreds of input elements in HTML.

JavaScript generates:

```text
Columns: A – J
Rows: 1 – 99
```

Each cell receives an ID such as:

```text
A1
B1
C1
A2
B2
```

These IDs allow formulas to reference other cells.

For example:

```text
=A1+B1
```

can retrieve the values stored in `A1` and `B1`, perform the calculation, and display the result.

## 🧮 Formula Evaluation

Formulas begin with an equals sign:

```text
=
```

When a cell changes, the application checks whether its value begins with `=`.

If it does, the formula is processed and evaluated.

The program supports arithmetic operators including:

```text
+
-
*
/
```

Multiplication and division are evaluated before addition and subtraction.

For example:

```text
=2+3*4
```

evaluates multiplication first before performing the addition.

## 🔗 Cell References

Cells can reference other spreadsheet cells directly.

Example:

```text
=A1
```

The program finds the cell with the ID `A1` and retrieves its value.

More complex expressions can combine several cells:

```text
=A1+B1
```

or:

```text
=A1*B1
```

This helped me understand how applications can connect UI elements to data and use identifiers to resolve relationships between values.

## 📐 Cell Ranges

The spreadsheet also supports ranges.

For example:

```text
=A1:A5
```

or:

```text
=A1:C3
```

The program parses the starting and ending cell coordinates and expands them into the corresponding cell values.

This required working with both:

- Numeric ranges
- Character ranges

JavaScript character codes are used to generate spreadsheet columns from letters such as `A` through `J`.

## 🧰 Supported Functions

The spreadsheet includes several custom functions.

### SUM

Adds all values together.

```text
=SUM(1,2,3,4)
```

Result:

```text
10
```

### AVERAGE

Calculates the average value.

```text
=AVERAGE(10,20,30)
```

Result:

```text
20
```

### MEDIAN

Calculates the median value from a group of numbers.

```text
=MEDIAN(1,5,10)
```

### EVEN

Returns the even values from a list.

```text
=EVEN(1,2,3,4,5,6)
```

### SOMEEVEN

Checks

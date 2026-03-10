# Week 5 – Data Preparation and Cleaning
## Data Cleaning Techniques

Data cleaning is the process of fixing errors, removing inconsistencies, and preparing datasets before analysis.

This document covers cleaning techniques using spreadsheets, command line tools, text editors, and specialized software.

---

# 1. Cleaning Data in Excel

Microsoft Excel contains several useful tools for preparing small to medium datasets.

## Find and Replace

The Find and Replace feature allows quick corrections across the dataset.

Shortcut:

```
Ctrl + H
```

Example use:

Removing unnecessary text such as extra words from country names.

---

## Changing Data Types

Sometimes numerical columns are stored as text.

To fix this:

1. Select the column
2. Change format to **Number**
3. Ensure formulas can operate correctly

Typical examples:

- population
- area
- density

---

## Removing Extra Spaces

The **TRIM** function removes unnecessary spaces from text.

Example:

```
=TRIM(D2)
```

This eliminates leading and trailing whitespace.

---

## Removing Blank Rows

Blank records can be removed efficiently.

Steps:

1. Select the dataset
2. Go to **Find & Select**
3. Choose **Go To Special**
4. Select **Blanks**
5. Delete the rows

---

## Removing Duplicate Entries

Duplicate values may occur during data collection.

Steps:

1. Select the column
2. Go to **Data → Remove Duplicates**

This ensures each entry appears only once.

---

# 2. Cleaning Data with OpenRefine

OpenRefine is an open-source tool designed for cleaning messy datasets.

It runs locally but is accessed through a web browser interface.

---

## Entity Resolution

Datasets may contain slightly different representations of the same entity.

Example:

```
xyz limited
xyz ltd
xyz ltd.
```

Although they refer to the same company, computers treat them as different entries.

---

## Faceting

OpenRefine provides **text facets** that display frequency counts of values.

This helps identify:

- spelling mistakes
- inconsistent formats
- duplicate entities

---

## Clustering

The clustering feature groups similar entries automatically.

It detects variations caused by:

- punctuation differences
- spacing
- abbreviations

Users can review and merge similar entries to standardize the dataset.

---

# 3. Dataset Inspection with pandas-profiling

The **pandas-profiling** library quickly generates an overview of a dataset.

It produces an HTML report containing key statistics.

Example:

```
from pandas_profiling import ProfileReport

profile = ProfileReport(df)
profile.to_file("report.html")
```

The report includes:

- dataset size
- missing values
- variable distributions
- correlations
- warnings

This helps identify problems before modeling.

---

# 4. Cleaning JSON Data with Visual Studio Code

Text editors can assist in quick data cleanup.

---

## Formatting JSON

To make JSON readable:

```
Ctrl + Shift + P → Format Document
```

This restructures the file automatically.

---

## Multi-Cursor Editing

Multiple entries can be edited simultaneously.

Shortcut:

```
Ctrl + D
```

---

## Selecting All Matches

```
Ctrl + F → Alt + Enter
```

This selects every instance of a value in the document.

---

## Sorting and Removing Duplicates

Commands available in the command palette:

```
Sort Lines Ascending
Delete Duplicate Lines
```

These tools help identify inconsistent values such as city name variations.

---

# 5. Cleaning Data with Unix Commands

Command-line utilities are effective for processing large files.

Examples include web server logs.

---

## Downloading Files

```
curl --location URL --output logs.gz
```

---

## Decompressing Files

```
gzip --decompress logs.gz
```

---

## Inspecting Data

```
head -n 5 logs.txt
tail -n 5 logs.txt
```

---

## Counting Records

```
wc -l logs.txt
```

---

## Extracting Fields

```
cut -d " " -f 1 logs.txt
```

---

## Finding Unique Entries

```
sort logs.txt | uniq --count
```

---

## Searching Patterns

```
grep "bot" logs.txt
```

---

## Editing Text

```
sed
```

can perform text replacements and formatting.

---

# Summary

Cleaning ensures data quality by fixing formatting errors, removing duplicates, handling missing values, and standardizing entries.

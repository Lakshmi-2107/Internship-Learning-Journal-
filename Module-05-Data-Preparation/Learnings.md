# Week 5 – Data Preparation
## Learnings

This week focused on preparing raw datasets for analysis using multiple tools.

---

# 1. Importance of Data Cleaning

Raw datasets frequently contain:

- duplicate entries
- inconsistent formatting
- missing values
- spelling errors

Cleaning ensures datasets are reliable for analysis.

---

# 2. Spreadsheet-Based Data Preparation

Excel provides powerful tools for:

- removing duplicates
- fixing text formatting
- splitting columns
- calculating derived metrics
- summarizing data with pivot tables

These tools are effective for moderate-sized datasets.

---

# 3. Automated Data Profiling

Libraries like **pandas-profiling** automatically analyze datasets.

Generated reports highlight:

- missing data
- extreme values
- variable correlations
- dataset statistics

This helps detect issues early in the workflow.

---

# 4. Specialized Cleaning Tools

OpenRefine provides advanced methods for identifying inconsistent entries.

Its clustering algorithms detect variations such as abbreviations and punctuation differences.

This makes it easier to standardize entity names.

---

# 5. Command Line Data Processing

Unix utilities provide fast processing for large datasets.

Examples include:

- downloading files with `curl`
- decompressing files with `gzip`
- counting records with `wc`
- searching patterns with `grep`
- sorting and aggregating values with `sort` and `uniq`

These tools are especially useful for log analysis.

---

# 6. Working with APIs

Many datasets are available through web APIs.

Python scripts can retrieve data, convert JSON responses into structured objects, and analyze them programmatically.

---

# 7. Media and Image Processing

Libraries like **Pillow** allow image manipulation tasks such as resizing, cropping, and applying filters.

Tools like **FFmpeg** extend these capabilities to video and audio processing.

---

# 8. Text Editors for Data Cleaning

Editors such as Visual Studio Code can perform quick corrections using:

- multi-cursor editing
- batch search and replace
- sorting lines
- removing duplicate values

---

# Key Takeaways

Important lessons from this module include:

- cleaning is essential before analysis
- multiple tools exist for different dataset sizes
- automated profiling tools help detect problems early
- command line utilities provide efficient large-scale processing
- transformation techniques convert raw data into meaningful insights

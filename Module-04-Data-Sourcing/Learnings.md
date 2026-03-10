# Module 4 – Data Sourcing
## Learnings

This module focuses on collecting and preparing data from multiple sources using scraping tools, APIs, and AI techniques.

---

# 1. Semantic Search Project

A semantic search prototype was developed using marketing articles from Insider Intelligence.

Dataset:

- 369 archive pages
- approximately 7000 articles

Traditional search engines such as **ElasticSearch** rely on keyword matching.

Semantic search instead understands query meaning and returns contextually relevant results.

Each search result includes a similarity score.

---

# 2. Web Scraping Process

Since direct access to the dataset was unavailable, articles were scraped from the website.

Steps:

1. collect article URLs from archive pages
2. download each article page
3. extract title and main content
4. store results in structured format

Libraries used:

- HTTPX
- BeautifulSoup
- lxml
- XPath

---

# 3. Data Caching

Caching stores downloaded pages locally.

Benefits:

- avoids repeated downloads
- reduces server load
- allows interrupted scraping to resume

---

# 4. Data Structuring

Extracted content was stored in JSON format.

Example:

```
{
"title": "Example Article",
"content": "Article text"
}
```

Structured data improves downstream processing.

---

# 5. Excel Web Data Extraction

Excel can also fetch data directly from websites.

Steps:

1. open Excel
2. go to Data tab
3. select Get Data
4. choose From Web
5. paste the URL
6. select table in Navigator
7. transform data in Power Query

The data connection allows refreshing to obtain updated information.

---

# 6. PDF Data Extraction

PDF files can be scraped using BeautifulSoup and Tabula.

Process:

1. scrape PDF links from a webpage
2. download PDFs
3. extract tables using Tabula
4. convert tables into CSV

Example:

```
tabula.read_pdf("file.pdf", pages=18)
```

Complex layouts may require specifying extraction areas.

---

# 7. Debugging Techniques

Useful debugging practices include:

Print Statements  
Helps verify intermediate values.

Breakpoints  
Allow interactive debugging.

Rubber Duck Debugging  
Explaining the problem aloud helps clarify thinking.

LLMs such as ChatGPT can also assist in debugging.

---

# 8. Experimental Learning

Side projects such as “Friday night experiments” encourage creativity and innovation.

Even unsuccessful experiments contribute to learning.

---

# Data Pipeline Diagram

```
Data Sources
   │
   ▼
Web Pages / APIs / PDFs
   │
   ▼
Data Collection
(HTTPX, BeautifulSoup, Excel Web Connector)
   │
   ▼
Data Extraction
(XPath, lxml, Tabula, LLM extraction)
   │
   ▼
Data Cleaning
(Python scripts, Power Query)
   │
   ▼
Structured Storage
(JSON / CSV / Markdown)
   │
   ▼
AI Processing
(Semantic Search / LLM analysis)
```

---

# Overall Learning

Key skills learned:

- web scraping large datasets
- extracting structured information
- using APIs for data sourcing
- building semantic search prototypes
- debugging effectively
- using AI tools for data extraction

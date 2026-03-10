# Module 4 – Data Sourcing
## APIs and Tools Used

This document describes the APIs, libraries, and tools used for collecting and processing data from various sources.

---

# 1. GitHub Actions

GitHub Actions is used to automate workflows directly inside a repository.

## Setting up Scheduled Workflows

Workflow files are stored inside:

.github/workflows/main.yml

Example configuration:

```yaml
name: Scheduled Workflow

on:
  schedule:
    - cron: "0 12 * * 6,0"

jobs:
  run-script:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - name: Run Script
        run: python script.py
```

## CRON Syntax

CRON expressions define when automated workflows run.

Example:

```
0 12 * * 6,0
```

This runs the workflow at **12:00 UTC every Saturday and Sunday**.

Important notes:

- GitHub schedules run using **UTC time**
- Jobs may not execute exactly at the scheduled moment
- Execution timing may vary depending on server load

Use cases:

- vulnerability scanning
- automated deployments
- dataset updates
- scheduled scripts

---

# 2. Nominatim Geocoding API

The Nominatim API converts location text into geographic coordinates using OpenStreetMap.

## Installation

```
pip install geopy
```

## Example

```python
from geopy.geocoders import Nominatim

geolocator = Nominatim(user_agent="geo_app")

location = geolocator.geocode("IIT Madras")

print(location.latitude)
print(location.longitude)
print(location.address)
```

Returned information may include:

- latitude
- longitude
- full address
- bounding box
- place class
- place type

---

# 3. Gemini AI Studio

Gemini AI Studio can extract structured information from images and video frames.

## Screen Scraping Method

1. Record a webpage while scrolling
2. Capture frames from the video
3. Send frames to Gemini AI Studio
4. Extract structured information as JSON

Advantages:

- extremely low cost
- efficient data extraction
- useful for visually structured content

Example: processing **1000 images costs around 1.8 cents**.

---

# 4. LLM-Based Scraping (OpenAI)

Large Language Models can also extract structured information from web pages.

Workflow:

1. Fetch webpage HTML
2. Send HTML content to an LLM
3. Ask the model to extract specific fields
4. Receive structured JSON output

Example concept:

```python
import openai

response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[
        {"role":"user","content":"Extract article title and content"}
    ]
)
```

Advantages:

- simplifies complex parsing
- works with messy HTML
- produces structured outputs

---

# 5. Markdown

Markdown is a lightweight text formatting language widely used in documentation.

Uses:

- GitHub documentation
- README files
- dataset preparation
- text indexing

Example:

```
# Heading
## Subheading
- bullet point
```

---

# 6. MarkItDown

MarkItDown is a Microsoft tool used to convert documents into Markdown.

Supported formats:

- PDF
- Word
- PowerPoint
- Excel
- images (OCR)
- HTML
- XML
- JSON
- CSV
- audio

Installation:

```
pip install markitdown
```

Example:

```python
from markitdown import MarkItDown

md = MarkItDown()
result = md.convert("file.pdf")

print(result.text)
```

---

# 7. Web Scraping Libraries

## HTTPX

HTTPX is a modern Python HTTP client used for downloading web pages.

Advantages:

- asynchronous support
- efficient networking
- improved performance

---

## BeautifulSoup

BeautifulSoup parses HTML and extracts elements.

Example:

```python
from bs4 import BeautifulSoup
```

Used for extracting:

- article titles
- text content
- links
- metadata

---

## lxml and XPath

lxml parses HTML/XML documents.

XPath selects elements based on document structure.

These tools are useful for extracting structured content from webpages.

---

# 8. Tabula

Tabula extracts tables from PDF documents.

Example:

```python
import tabula

df = tabula.read_pdf("file.pdf", pages=18)
```

The extracted tables can be converted into CSV files.

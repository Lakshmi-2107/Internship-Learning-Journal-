# Week 5 – Data Preparation
## Data Transformation Techniques

After cleaning data, transformation methods are used to prepare it for analysis.

---

# 1. Calculating Ratios

Derived metrics help compare related values.

Example formulas:

### Metro Area vs City Area

```
=G2/D2
```

### Metro Population vs City Population

```
Metro Population / City Population
```

### Population Density

```
Population / Area
```

These measures help analyze urban development patterns.

---

# 2. Pivot Tables

Pivot tables summarize large datasets quickly.

Steps:

1. Select dataset
2. Go to **Insert → Pivot Table**
3. Choose rows and values

Examples:

- list unique countries
- count records
- aggregate population totals

---

# 3. Detecting Outliers

Charts generated from pivot tables can reveal unusual values.

Examples:

- extremely large cities
- unusually dense metropolitan regions

---

# 4. Text to Columns

Scraped datasets often store multiple values in a single column.

Excel’s **Text to Columns** tool separates them.

Steps:

1. Select column
2. Go to **Data → Text to Columns**
3. Choose delimiter

Examples of delimiters:

- parentheses
- hyphens
- commas

---

# 5. Time-Based Transformations

Date values can be grouped by week or month.

Examples:

```
=WEEKNUM(Date)
```

```
=TEXT(Date,"mmm-yy")
```

---

# 6. Conditional Formatting

Conditional formatting highlights important values.

Example:

- high values → red
- low values → green

This makes trends easier to detect.

---

# 7. Sparklines and Data Bars

Small visual elements inside cells help show trends.

Examples:

- sparklines for time trends
- data bars for comparisons

---

# 8. Fetching Data from APIs

Python can retrieve data from JSON APIs.

Example using the **requests** library:

```
import requests
import json

response = requests.get(url)
data = response.json()
```

Steps involved:

1. request API data
2. convert JSON into Python objects
3. analyze values
4. sort or filter results

Rate limiting may be handled using:

```
time.sleep()
```

---

# 9. Image Processing with Pillow

Pillow is a Python library for image manipulation.

Example:

```
from PIL import Image

img = Image.open("image.jpg")
img.show()
```

Capabilities include:

- resizing images
- rotating images
- converting formats
- applying filters

Batch processing can be done using loops.

---

# 10. Media Processing with FFmpeg

FFmpeg is a command-line tool used for audio and video processing.

Basic syntax:

```
ffmpeg -i inputfile outputfile
```

Common uses:

- converting file formats
- resizing videos
- cropping frames
- adjusting audio levels

Examples:

```
ffmpeg -i video.avi video.mp4
```

```
ffmpeg -vf scale=1280:720
```

FFmpeg also supports many filters for video and audio editing.

---

# Summary

Data transformation converts cleaned data into analytical formats by calculating metrics, reorganizing columns, and generating visual summaries.

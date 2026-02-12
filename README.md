# 📝 Python Web Scraping & Regex Practice
## Overview

## This repository contains practice exercises for:

Web scraping using Python
Extracting and parsing HTML content with BeautifulSoup
Sending HTTP requests with Requests
Text extraction and processing
Using Regular Expressions (Regex) for pattern matching

Note: This is a learning/practice repository, not a full project.

### 🛠 Technologies Used

Python 3.x
requests — to fetch web pages
BeautifulSoup (from bs4) — to parse HTML and navigate the DOM
re — Python’s regular expressions library
pandas — for structuring extracted data

### 🔹 Web Scraping Practice

Steps Learned:

Fetching Web Page Content
```
import requests
page = requests.get('https://webscraper.io/test-sites/e-commerce/allinone/phones')
print(page.status_code)  # 200 means successful connection
```

Parsing HTML
```
from bs4 import BeautifulSoup
soup = BeautifulSoup(page.text, 'html')
```

Accessing HTML Tags and Attributes
```
soup.title           # <title>Allinone | Web Scraper Test Sites</title>
soup.title.string    # 'Allinone | Web Scraper Test Sites'
soup.header.attrs    # {'role': 'banner', 'class': [...], 'id': 'navbar-top'}
```

Finding Elements
```
soup.find('h1')                        # Finds first <h1> tag
soup.find_all('a', 'title')            # Finds all <a> tags with class 'title'
```

Extracting Text
```
all_phone_titles = soup.find_all('a', 'title')
all_titles = [title.text for title in all_phone_titles]
```

Organizing Data with Pandas
```
import pandas as pd
pd.DataFrame(all_titles)
```
### 🔹 Regular Expressions (Regex) Practice

Regex is used for searching, matching, and manipulating text.

Common Operations:
```
re.findall(pattern, string) — find all matches

re.search(pattern, string) — find first match

re.sub(pattern, replacement, string) — replace text

re.split(pattern, string) — split text by pattern
```
Examples:
```
import re

quote = "My phone number is 469-961-6124"

# Extract all digits
re.findall("\d", quote)  # ['4','6','9','9','6','1','6','1','2','4']

# Extract words
re.findall("\w", quote)

# Find specific word patterns
re.findall(r"\bpython", "I love python and pythonlove")  # ['python', 'python']
```

### Metacharacters Practiced:

Symbol	Meaning
\d	Digit (0-9)
\w	Word character
\W	Non-word character
.	Any character except newline
*	0 or more repetitions
+	1 or more repetitions
?	0 or 1 repetition
^	Start of string
$	End of string
\b	Word boundary
\B	Not a word boundary

### ✅ Learning Outcomes

Understand how web scraping works using Requests and BeautifulSoup
Learn to navigate HTML DOM and extract text/attributes
Practice regex patterns for text processing
Learn to structure scraped data using Pandas
Understand real-world applications: data extraction, preprocessing, and analysis
This is a practice exercise, perfect for reinforcing Python skills for:
Web scraping
Text processing
Data analysis pipelines

# dont forget to all regex, datascraping from web

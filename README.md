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


## 🧠 Python Regex Modifiers & Web Scraping Practice

✅ Regex match object methods

✅ Regex modifiers (flags)

✅ Real-world regex use cases

✅ Data extraction from structured text

✅ Web scraping with BeautifulSoup

✅ Building datasets using Pandas

This is a practice-based learning file, designed to strengthen understanding of pattern matching, text extraction, and HTML parsing.

 ### 📌 Regex Match Object Methods

This section demonstrates how to work with match objects returned by re.search().

Example:
```
result = re.search(r"(\b[A-Z]+\b).*(\b\d+\b)", string)
```
### Methods Practiced:
Method	Purpose
`group()`	Returns full matched string
`group(n)`	Returns specific captured group
`groups()`	Returns tuple of all captured groups
`start()`	Starting index of match
`end()`	Ending index of match
`span()`	Returns (start, end)
Learning Outcome:

Understanding how captured groups work and how to extract specific parts of matched text.

###  🚩 Regex Modifiers (Flags)

**Regex modifiers control how patterns behave.**

### Modifiers Practiced
Modifier	Description
re.I	Case-insensitive matching
re.M	Multi-line matching (^ and $ apply per line)
re.S	Dot matches newline (. matches \n)
re.L	Locale-based matching
re.U	Unicode-aware matching
re.X	Allows whitespace and comments inside regex
### 🔹 Case-Insensitive Matching
``
re.findall(r"\b[a-z]+\b", quote, re.I)
``

Matches both uppercase and lowercase words.

🔹 Multi-line Matching
```
re.findall(r"^\w{5,8}", target, re.M)
```

Allows ^ to match the start of each line instead of only the full string.

🔹 Dotall Modifier
```
re.findall(r".+", string, re.S)
```

Allows . to match newline characters.

### Real-World Regex Use Cases

This section focuses on extracting structured data such as:

📧 Email addresses

📱 Phone numbers

🌐 Email domains

📞 Area codes

📧 Extracting Emails
```
re.findall(r"[\w\.+]+@[\w\.+]+", random_text)
```

Extracts complete email addresses.

🌐 Extracting Email Domains
```
re.findall(r"@([a-zA-Z]+)", email)
```

Uses capturing groups to extract only the domain name.

📱 Extracting Phone Numbers
```
re.findall(r"\d{3}-\d{3}-\d{4}", random_text)
```

Matches US-style phone numbers.

📞 Extracting Area Codes
```
area_code_pattern = r'(\d{3})'
```

Uses a loop + re.search() to extract area codes from multiple phone numbers.

### 🌍 Web Scraping + Pandas

This section demonstrates scraping structured tabular data from:

Website Used:
```
https://www.worldometers.info/world-population/population-by-country/
```
### Steps Performed

1️⃣ Send HTTP Request
```
page = requests.get(url)
```
2️⃣ Parse HTML
```
soup = BeautifulSoup(page.text, 'html')
```
3️⃣ Extract Table Headers
```
world_columns = table.find_all('th')
```
4️⃣ Extract Table Rows
```
world_rows = table.find_all('tr')
```
5️⃣ Store Data in Pandas DataFrame
```
df = pd.DataFrame(columns = world_columns_titles)
```
6️⃣ Export to CSV
```
df.to_csv("World_Population_Scraped.csv", index=False)
```

### 📊 Final Output

Extracted 233 countries

12 data columns including:

Country

Population 2026

Yearly Change

Density

Fertility Rate

Median Age

World Share

Exported dataset to CSV

### 🧩 Skills Strengthened

Understand how web scraping works using Requests and BeautifulSoup
Learn to navigate HTML DOM and extract text/attributes
Practice regex patterns for text processing
Learn to structure scraped data using Pandas
Understand real-world applications: data extraction, preprocessing, and analysis
This is a practice exercise, perfect for reinforcing Python skills for:
Web scraping
Text processing
Data analysis pipelines

✔ Advanced Regex Grouping
✔ Regex Modifiers & Behavior Control
✔ Pattern Extraction from Real Data
✔ Email & Phone Parsing
✔ Loop + Regex Integration
✔ HTML Table Scraping
✔ Data Structuring with Pandas
✔ CSV File Export

### 🎯 Key Takeaways

This practice file reinforces:

Deep understanding of regex engine behavior

Ability to extract structured information from messy text

How regex integrates into real-world workflows

Combining scraping + text parsing + data storage

Building mini data pipelines using Python

# Python APIs and Data Collection

## 📚 Module Overview

This module focuses on data acquisition techniques using Python, covering API integration, HTTP requests, web scraping, and real-world data collection projects. You'll learn how to access external data sources, handle different data formats, and build robust data collection pipelines for data science and AI applications.

## 🎯 Learning Objectives

By the end of this module, you will be able to:

- Understand and work with RESTful APIs
- Make HTTP requests and handle responses effectively
- Implement web scraping techniques using BeautifulSoup
- Parse and process different data formats (JSON, XML, CSV)
- Handle authentication and rate limiting
- Build robust data collection pipelines
- Apply data collection techniques to real-world projects
- Implement error handling and data validation

## 📁 Module Contents

### 1. [Introduction to APIs](./intro-to-api.ipynb)
**Understanding APIs and RESTful services**

**Topics Covered:**
- What are APIs and their importance
- RESTful API principles and HTTP methods
- API authentication and authorization
- Common data formats (JSON, XML)
- API documentation and endpoints
- Rate limiting and best practices
- Error handling and status codes
- API testing and debugging

**Key Skills:**
- Understand API concepts and architecture
- Read and interpret API documentation
- Handle authentication mechanisms
- Work with different data formats

### 2. [HTTP Requests](./http-requests.ipynb)
**Making API calls and handling responses**

**Topics Covered:**
- HTTP protocol fundamentals
- Making requests with requests library
- HTTP methods (GET, POST, PUT, DELETE)
- Request headers and parameters
- Response handling and status codes
- Session management and cookies
- Timeout and retry mechanisms
- Advanced request techniques

**Key Skills:**
- Make HTTP requests programmatically
- Handle different response types
- Implement session management
- Build robust request handling

### 3. [Web Scraping](./web-scraping.ipynb)
**Extracting data from websites**

**Topics Covered:**
- Web scraping fundamentals and ethics
- HTML structure and parsing
- BeautifulSoup library usage
- CSS selectors and XPath
- Handling dynamic content
- Anti-scraping measures
- Data extraction techniques
- Web scraping best practices

**Key Skills:**
- Parse HTML and extract data
- Use CSS selectors effectively
- Handle dynamic web content
- Implement ethical scraping practices

### 4. [GDP Data Project](./gdp-data-project.ipynb)
**Real-world data collection and analysis**

**Topics Covered:**
- Multi-source data collection
- Data cleaning and preprocessing
- Data integration and merging
- Statistical analysis and visualization
- Project structure and organization
- Documentation and reporting
- Best practices for data projects

**Key Skills:**
- Integrate multiple data sources
- Clean and preprocess collected data
- Perform comprehensive data analysis
- Create professional data reports

## 🛠️ Prerequisites

- Basic Python programming knowledge
- Understanding of data structures (lists, dictionaries)
- Familiarity with Jupyter notebooks
- Completion of previous modules recommended

## 📦 Required Libraries

```python
# HTTP requests and API handling
import requests
from requests.auth import HTTPBasicAuth, HTTPBearerAuth
import json
import xml.etree.ElementTree as ET

# Web scraping
from bs4 import BeautifulSoup
import lxml
import html5lib

# Data manipulation
import pandas as pd
import numpy as np

# Visualization
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
import plotly.graph_objects as go

# Utilities
import time
import random
from datetime import datetime, timedelta
import logging
from typing import Dict, List, Any, Optional
```

## 🚀 Getting Started

1. **Navigate to this directory**:
   ```bash
   cd python-APIs-and-data-collection
   ```

2. **Install required packages**:
   ```bash
   pip install requests beautifulsoup4 lxml html5lib pandas numpy matplotlib seaborn plotly
   ```

3. **Set up API keys** (if needed):
   ```python
   # Create a config file for API keys
   API_KEYS = {
       'openweathermap': 'your_api_key_here',
       'newsapi': 'your_api_key_here'
   }
   ```

4. **Start with intro-to-api.ipynb** and progress sequentially

## 📖 Learning Path

### Week 1: API Fundamentals
- **Day 1-2**: Understanding APIs and REST principles
- **Day 3-4**: Authentication and data formats
- **Day 5-7**: API documentation and testing

### Week 2: HTTP Requests
- **Day 1-2**: HTTP protocol and requests library
- **Day 3-4**: Advanced request techniques
- **Day 5-7**: Session management and error handling

### Week 3: Web Scraping
- **Day 1-2**: HTML parsing and BeautifulSoup
- **Day 3-4**: CSS selectors and data extraction
- **Day 5-7**: Anti-scraping measures and best practices

### Week 4: GDP Data Project
- **Day 1-2**: Data collection and integration
- **Day 3-4**: Data cleaning and analysis
- **Day 5-7**: Visualization and reporting

## 💡 Key Concepts

### API Requests
```python
import requests
import json

# Basic GET request
response = requests.get('https://api.example.com/data')
data = response.json()

# POST request with data
payload = {'key1': 'value1', 'key2': 'value2'}
response = requests.post('https://api.example.com/submit', json=payload)

# Request with authentication
headers = {'Authorization': 'Bearer your_token_here'}
response = requests.get('https://api.example.com/protected', headers=headers)

# Request with parameters
params = {'q': 'python', 'page': 1}
response = requests.get('https://api.example.com/search', params=params)
```

### Web Scraping
```python
from bs4 import BeautifulSoup
import requests

# Fetch webpage
url = 'https://example.com'
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html.parser')

# Extract data using CSS selectors
titles = soup.select('h1.title')
links = soup.find_all('a', href=True)

# Extract specific data
for title in titles:
    print(title.text.strip())

# Handle pagination
for page in range(1, 6):
    url = f'https://example.com/page/{page}'
    response = requests.get(url)
    soup = BeautifulSoup(response.content, 'html.parser')
    # Extract data from each page
    time.sleep(1)  # Be respectful with requests
```

### Data Processing
```python
import pandas as pd
import json

# Load JSON data
with open('data.json', 'r') as f:
    data = json.load(f)

# Convert to DataFrame
df = pd.DataFrame(data)

# Clean and process data
df['date'] = pd.to_datetime(df['date'])
df = df.dropna()
df = df.sort_values('date')

# Save processed data
df.to_csv('processed_data.csv', index=False)
```

## 🔐 Authentication Methods

### API Key Authentication
```python
# Using API key in headers
headers = {'X-API-Key': 'your_api_key'}
response = requests.get('https://api.example.com/data', headers=headers)

# Using API key in URL parameters
params = {'api_key': 'your_api_key'}
response = requests.get('https://api.example.com/data', params=params)
```

### OAuth Authentication
```python
from requests_oauthlib import OAuth2Session

# OAuth 2.0 flow
client_id = 'your_client_id'
client_secret = 'your_client_secret'
redirect_uri = 'https://your-app.com/callback'

oauth = OAuth2Session(client_id, redirect_uri=redirect_uri)
authorization_url, state = oauth.authorization_url('https://api.example.com/oauth/authorize')

# After user authorization
token = oauth.fetch_token('https://api.example.com/oauth/token', 
                         client_secret=client_secret)
```

## 🛡️ Best Practices

### Rate Limiting
```python
import time
from requests.adapters import HTTPAdapter
from requests.packages.urllib3.util.retry import Retry

# Implement retry strategy
retry_strategy = Retry(
    total=3,
    backoff_factor=1,
    status_forcelist=[429, 500, 502, 503, 504],
)

adapter = HTTPAdapter(max_retries=retry_strategy)
session = requests.Session()
session.mount("http://", adapter)
session.mount("https://", adapter)

# Add delays between requests
def make_request_with_delay(url, delay=1):
    response = session.get(url)
    time.sleep(delay)
    return response
```

### Error Handling
```python
import requests
from requests.exceptions import RequestException

def safe_api_request(url, max_retries=3):
    for attempt in range(max_retries):
        try:
            response = requests.get(url, timeout=10)
            response.raise_for_status()
            return response.json()
        except RequestException as e:
            print(f"Attempt {attempt + 1} failed: {e}")
            if attempt == max_retries - 1:
                raise
            time.sleep(2 ** attempt)  # Exponential backoff
```

## 📊 Projects and Exercises

### Mini-Projects
1. **Weather Data Collector**: Build a weather data collection system
2. **News Aggregator**: Create a news collection and analysis tool
3. **E-commerce Scraper**: Extract product information from e-commerce sites
4. **Social Media API**: Integrate with social media APIs

### Exercises
- Create a function to fetch data from multiple APIs
- Build a web scraper for a specific website
- Implement data validation for collected data
- Create a data pipeline with error handling

## 🆘 Troubleshooting

### Common Issues
1. **API Rate Limits**: Implement proper delays and retry logic
2. **Authentication Errors**: Check API keys and authentication methods
3. **HTML Structure Changes**: Use robust selectors and error handling
4. **Network Issues**: Implement timeout and retry mechanisms

### Debugging Tips
- Use `print(response.status_code)` to check HTTP status
- Print `response.text` to see raw response content
- Use browser developer tools to inspect HTML structure
- Test API endpoints with tools like Postman

## 📚 Additional Resources

### Documentation
- [Requests Library](https://requests.readthedocs.io/)
- [BeautifulSoup Documentation](https://www.crummy.com/software/BeautifulSoup/)
- [HTTP Status Codes](https://httpstatuses.com/)

### APIs for Practice
- [JSONPlaceholder](https://jsonplaceholder.typicode.com/) - Free fake API
- [OpenWeatherMap](https://openweathermap.org/api) - Weather data
- [NewsAPI](https://newsapi.org/) - News articles
- [GitHub API](https://developer.github.com/v3/) - GitHub data

### Tools
- [Postman](https://www.postman.com/) - API testing
- [Insomnia](https://insomnia.rest/) - API client
- [Scrapy](https://scrapy.org/) - Advanced web scraping framework

## 🎯 Next Steps

After completing this module:
- Move to **Python Working with Data** for data analysis tools
- Explore advanced web scraping with Scrapy
- Learn about data streaming and real-time APIs
- Consider building a complete data pipeline

## 🔍 Real-World Applications

### Data Science Applications
- **Market Research**: Collect competitor data and pricing information
- **Social Media Analysis**: Gather social media posts and engagement metrics
- **Financial Data**: Access stock prices and economic indicators
- **Research Data**: Collect academic papers and research data

### Business Applications
- **Competitive Intelligence**: Monitor competitor websites and products
- **Customer Feedback**: Collect reviews and ratings from various platforms
- **Market Trends**: Gather industry news and market data
- **Lead Generation**: Extract contact information from business directories

---

**Ready to collect and analyze real-world data? Let's dive in! 🌐📊** 
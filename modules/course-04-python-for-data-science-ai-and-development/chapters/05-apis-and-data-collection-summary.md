# Module 5: APIs and Data Collection

## Overview
Module 5 covered using APIs to access remote resources, HTTP fundamentals, basic web scraping techniques, handling common file formats, and collecting/processing time-series data. You practiced working with requests, JSON, Beautiful Soup, Pandas, and Plotly.

## Key Concepts

### APIs in Python
- An API is an interface enabling two software components to communicate.
- Simple APIs expose straightforward methods with minimal configuration.
- Typical workflow: import a client library, make HTTP requests, parse responses (often JSON) into Python objects.
- Pandas can act as a consumer of APIs/pipelines and process results into DataFrames.
- Creating a dictionary instance and passing it to `pd.DataFrame()` constructs a DataFrame.
- Useful DataFrame methods: `head(n)` to preview rows; `mean()` to compute column-wise means.

### REST and HTTP
- REST APIs use HTTP to access resources like storage, datasets, or AI services over the internet.
- HTTP requests use methods such as GET (retrieve), POST (create/submit), PUT (update), DELETE (remove).
- An HTTP message commonly carries JSON in the request/response body.
- HTTP responses include metadata (resource type, length) and the body.
- URLs locate resources and have three parts: scheme, base URL (internet address), and route; queries can modify results (e.g., filter by id or name).
- The `requests` library simplifies sending HTTP/1.1 requests and handling responses.

### Time series and visualization
- Pandas time series utilities help parse dates, index data by time, and resample/aggregate.
- Financial “daily candlesticks” can be retrieved and visualized with Plotly’s candlestick charts.

### Web scraping essentials
- Web pages use HTML (with CSS/JS). HTML is a tree of elements (tags) and text nodes.
- Tables are built with header/body rows and can be extracted with `pd.read_html`.
- Beautiful Soup parses HTML/XML into a navigable tree.
  - Create a `BeautifulSoup` object to parse a document.
  - `find_all` searches by tag, attributes, and/or text; returns an iterable (e.g., list) of matches.
  - `NavigableString` represents text nodes that support BS4 operations.

### Common file formats
- File formats define structure/encoding (e.g., `.txt`, `.csv`, `.json`, `.xml`, `.xlsx`).
- The extension indicates the format and typical tools needed to open it.
- Access CSV with Pandas (e.g., `pd.read_csv`); use appropriate libraries/methods for JSON, XML, and others.

## Practical Applications
- Pulling data from public REST APIs and transforming it into analysis-ready DataFrames.
- Parameterizing GET queries with URL query strings to refine results.
- Scraping structured content (tables, lists) from webpages when APIs are unavailable.
- Building time-series dashboards and exploratory visuals from remote data.

## Importance for Data Science
APIs unlock data and compute beyond local files. Mastering HTTP, JSON, scraping, and file formats—combined with Pandas and visualization—enables robust, automated data collection pipelines that feed downstream analysis and modeling.

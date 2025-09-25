# SpaceX Web Scraping from Wikipedia

**Reference:** `completed_assignements/10-02-spacex-web-scraping.ipynb`

## Overview
This lab focused on web scraping Falcon 9 and Falcon Heavy launch records from Wikipedia to collect historical launch data. The goal was to extract comprehensive launch information from the "List of Falcon 9 and Falcon Heavy launches" Wikipedia page.

## Key Objectives
- Extract Falcon 9 launch records HTML table from Wikipedia
- Parse the table and convert it into a Pandas DataFrame
- Handle complex HTML structure and data cleaning

## Web Scraping Process

### Target Source
- **Wikipedia Page:** "List of Falcon 9 and Falcon Heavy launches"
- **Static URL:** `https://en.wikipedia.org/w/index.php?title=List_of_Falcon_9_and_Falcon_Heavy_launches&oldid=1027686922`
- **Snapshot Date:** June 9, 2021

### Technical Implementation
- **Libraries Used:** BeautifulSoup4, requests, pandas, re, unicodedata
- **HTTP Headers:** Configured to mimic browser requests
- **Target Table:** Third table in the HTML (index 2)

## Data Extraction Functions

### Helper Functions Created
1. **`date_time()`** - Extracts date and time from table cells
2. **`booster_version()`** - Extracts booster version information
3. **`landing_status()`** - Extracts landing status
4. **`get_mass()`** - Extracts payload mass with kg units
5. **`extract_column_from_header()`** - Cleans column headers from HTML

### Data Processing Challenges
- **Complex HTML Structure:** Nested elements, references, and annotations
- **Data Cleaning:** Removed reference links (e.g., `B0004.1[8]`)
- **Missing Values:** Handled `N/A` entries appropriately
- **Inconsistent Formatting:** Normalized text using unicodedata

## Extracted Data Structure

### Column Names Identified
- Flight No.
- Date and time (UTC)
- Version, Booster
- Launch site
- Payload
- Payload mass
- Orbit
- Customer
- Launch outcome
- Booster landing

### Data Processing Results
- **Total Records Extracted:** Multiple launch records from all tables
- **Data Quality:** Handled HTML artifacts and reference links
- **Format Standardization:** Cleaned and normalized all text fields

## Key Data Points Extracted

### Launch Information
- **Flight Numbers:** Sequential launch numbering
- **Dates/Times:** UTC timestamps for each launch
- **Booster Versions:** Detailed version information (e.g., F9 v1.0, F9 v1.1)
- **Launch Sites:** Specific launch facilities (CCAFS SLC-40, VAFB SLC-4E, KSC LC-39A)

### Payload Details
- **Payload Names:** Specific payload/satellite names
- **Payload Mass:** Mass in kg with proper unit handling
- **Orbit Types:** Target orbits (LEO, GTO, SSO, etc.)
- **Customers:** Launch customers (NASA, commercial, etc.)

### Mission Outcomes
- **Launch Outcomes:** Success/failure status
- **Booster Landing:** Landing success and method (ground pad, drone ship, ocean)

## Data Quality Improvements

### Text Processing
- **Unicode Normalization:** Used `unicodedata.normalize("NFKD")`
- **Reference Removal:** Stripped Wikipedia reference links `[.*?]`
- **Whitespace Handling:** Proper trimming and cleaning

### Validation
- **Flight Number Validation:** Ensured numeric flight numbers
- **Data Consistency:** Maintained consistent formatting across records
- **Missing Data Handling:** Preserved None values where appropriate

## Key Findings
- Successfully extracted comprehensive launch records from Wikipedia
- Handled complex HTML structure with nested elements and references
- Created clean, structured dataset with standardized formatting
- Established foundation for historical launch analysis

## Output
- **CSV Export:** `spacex_web_scraped.csv` - Cleaned dataset from web scraping
- **Data Structure:** Well-formatted DataFrame with consistent column types
- **Coverage:** Historical launch data from early Falcon 9 missions

## Technical Challenges Overcome
- **HTML Complexity:** Parsed nested table structures with multiple elements
- **Data Cleaning:** Removed Wikipedia-specific formatting and references
- **Encoding Issues:** Handled Unicode characters and special formatting
- **Table Selection:** Identified correct table among multiple HTML tables

This web scraping phase provided valuable historical context and additional data points that complemented the API-collected data, creating a more comprehensive dataset for the SpaceX landing prediction analysis.

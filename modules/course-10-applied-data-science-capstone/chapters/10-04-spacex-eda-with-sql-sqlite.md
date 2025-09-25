# SpaceX EDA with SQL and SQLite

**Reference:** `completed_assignements/10-04-spacex-eda-with-sql-sqlite.ipynb`

## Overview
This lab focused on performing exploratory data analysis using SQL queries on the SpaceX dataset. The goal was to demonstrate SQL proficiency while extracting meaningful insights about SpaceX launch patterns, payload characteristics, and mission outcomes.

## Key Objectives
- Load SpaceX dataset into SQLite database
- Execute SQL queries to answer specific business questions
- Analyze launch patterns, payload data, and mission outcomes

## Database Setup

### Technical Implementation
- **Database:** SQLite (`my_data1.db`)
- **Table:** `SPACEXTABLE` (cleaned version of `SPACEXTBL`)
- **Data Source:** `https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/labs/module_2/data/Spacex.csv`
- **Libraries:** SQLAlchemy, pandas, sqlite3, ipython-sql

### Data Processing
- **Initial Load:** Created `SPACEXTBL` from CSV
- **Data Cleaning:** Removed blank rows with `Date is not null`
- **Final Table:** `SPACEXTABLE` with clean data

## SQL Analysis Results

### Task 1: Unique Launch Sites
**Query:** `SELECT DISTINCT "Launch_Site" FROM SPACEXTABLE;`
- **Findings:** Identified all unique launch facilities
- **Launch Sites:** CCAFS SLC-40, VAFB SLC-4E, KSC LC-39A

### Task 2: CCA Launch Site Records
**Query:** `SELECT * FROM SPACEXTABLE WHERE "Launch_Site" LIKE 'CCA%' LIMIT 5;`
- **Findings:** Retrieved 5 records from CCAFS launch sites
- **Pattern:** CCAFS SLC-40 is the primary launch facility

### Task 3: NASA CRS Payload Mass
**Query:** `SELECT SUM(CAST("Payload_Mass__kg_" AS INTEGER)) AS total_payload_mass FROM SPACEXTABLE WHERE "Customer" = 'NASA (CRS)';`
- **Findings:** Total payload mass carried for NASA Commercial Resupply Services
- **Business Value:** Quantified NASA partnership payload capacity

### Task 4: F9 v1.1 Average Payload
**Query:** `SELECT AVG(CAST("Payload_Mass__kg_" AS INTEGER)) AS avg_payload_mass FROM SPACEXTABLE WHERE "Booster_Version" = 'F9 v1.1';`
- **Findings:** Average payload mass for Falcon 9 v1.1 booster
- **Technical Insight:** Performance characteristics of specific booster version

### Task 5: First Successful Ground Pad Landing
**Query:** `SELECT MIN("Date") AS first_success_ground_pad FROM SPACEXTABLE WHERE "Landing_Outcome" = 'Success (ground pad)';`
- **Findings:** Historical milestone - first successful ground pad landing
- **Significance:** Key achievement in SpaceX reusability program

### Task 6: Heavy Payload Drone Ship Success
**Query:** `SELECT DISTINCT "Booster_Version" FROM SPACEXTABLE WHERE "Landing_Outcome" = 'Success (drone ship)' AND CAST("Payload_Mass__kg_" AS INTEGER) > 4000 AND CAST("Payload_Mass__kg_" AS INTEGER) < 6000;`
- **Findings:** Booster versions successful with medium-heavy payloads (4000-6000 kg)
- **Technical Insight:** Payload mass impact on landing success

### Task 7: Mission Outcome Distribution
**Query:** `SELECT "Mission_Outcome", COUNT(*) AS total FROM SPACEXTABLE GROUP BY "Mission_Outcome";`
- **Findings:** Success vs failure rates across all missions
- **Business Value:** Overall mission reliability metrics

### Task 8: Maximum Payload Booster Versions
**Query:** `SELECT DISTINCT "Booster_Version" FROM SPACEXTABLE WHERE CAST("Payload_Mass__kg_" AS INTEGER) = (SELECT MAX(CAST("Payload_Mass__kg_" AS INTEGER)) FROM SPACEXTABLE);`
- **Findings:** Booster versions capable of carrying maximum payload
- **Technical Insight:** Payload capacity limits by booster version

### Task 9: 2015 Drone Ship Failures
**Query:** `SELECT substr("Date", 6, 2) AS month, "Landing_Outcome", "Booster_Version", "Launch_Site" FROM SPACEXTABLE WHERE substr("Date", 0, 5) = '2015' AND "Landing_Outcome" = 'Failure (drone ship)' ORDER BY month;`
- **Findings:** Monthly breakdown of drone ship landing failures in 2015
- **Historical Insight:** Learning curve during early reusability attempts

### Task 10: Landing Outcome Ranking (2010-2017)
**Query:** `SELECT "Landing_Outcome", COUNT(*) AS outcome_count FROM SPACEXTABLE WHERE "Date" BETWEEN '2010-06-04' AND '2017-03-20' GROUP BY "Landing_Outcome" ORDER BY outcome_count DESC;`
- **Findings:** Ranking of landing outcomes during early SpaceX period
- **Historical Analysis:** Evolution of landing success rates

## Key Insights from SQL Analysis

### Launch Site Patterns
- **CCAFS SLC-40:** Primary launch facility
- **VAFB SLC-4E:** Specialized for polar orbits
- **KSC LC-39A:** Third launch facility

### Payload Characteristics
- **NASA CRS:** Significant payload mass contribution
- **F9 v1.1:** Specific performance metrics identified
- **Maximum Payload:** Booster version capabilities

### Landing Success Evolution
- **Historical Milestones:** First successful ground pad landing identified
- **Learning Curve:** 2015 drone ship failure patterns
- **Success Rates:** Overall mission and landing success metrics

### Technical Performance
- **Payload Mass Impact:** Relationship between payload mass and landing success
- **Booster Versions:** Performance differences across versions
- **Mission Outcomes:** Success/failure distribution analysis

## Business Value

### Cost Analysis
- **Reusability Impact:** Landing success directly affects launch costs
- **Competitive Advantage:** $62M vs $165M launch cost difference
- **Market Position:** SpaceX's cost advantage through reusability

### Operational Insights
- **Launch Site Utilization:** Facility usage patterns
- **Payload Capacity:** Booster version capabilities
- **Success Rates:** Mission reliability metrics

## Technical Achievements
- **SQL Proficiency:** Demonstrated complex query capabilities
- **Data Analysis:** Extracted meaningful business insights
- **Database Management:** Efficient data storage and retrieval

## Output
- **Database:** `my_data1.db` with clean SpaceX data
- **Analysis:** Comprehensive SQL-based insights
- **Queries:** 10 complex analytical queries executed

This SQL analysis phase provided deep insights into SpaceX operations, launch patterns, and performance metrics, establishing a solid foundation for understanding the business context of the landing prediction problem.

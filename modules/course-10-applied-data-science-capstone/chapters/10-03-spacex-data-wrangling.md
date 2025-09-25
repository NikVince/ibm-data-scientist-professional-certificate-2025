# SpaceX Data Wrangling and Label Creation

**Reference:** `completed_assignements/10-03-spacex-data-wrangling.ipynb`

## Overview
This lab focused on performing exploratory data analysis (EDA) and creating training labels for the SpaceX Falcon 9 landing prediction model. The primary goal was to understand the data patterns and convert landing outcomes into binary classification labels.

## Key Objectives
- Perform exploratory data analysis
- Determine training labels for supervised learning
- Convert landing outcomes into binary classification (1 = success, 0 = failure)

## Data Analysis Process

### Dataset Loading
- **Source:** `https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/datasets/dataset_part_1.csv`
- **Initial Analysis:** Identified missing values and data types

### Data Quality Assessment
- **Missing Values Analysis:** Calculated percentage of missing values per column
- **Data Types:** Identified numerical vs categorical columns
- **Data Structure:** 90 records with mixed data types

## Key Findings from EDA

### Launch Site Analysis
**Task 1: Launch Site Distribution**
- **CCAFS SLC-40:** Most active launch site
- **VAFB SLC-4E:** Secondary launch facility
- **KSC LC-39A:** Third launch site
- **Pattern:** CCAFS SLC-40 dominates launch activity

### Orbit Type Analysis
**Task 2: Orbit Distribution**
- **LEO (Low Earth Orbit):** Most common orbit type
- **GTO (Geostationary Transfer Orbit):** Second most common
- **ISS (International Space Station):** Regular resupply missions
- **Other Orbits:** SSO, VLEO, ES-L1, HEO, MEO, GEO, PO

### Landing Outcome Analysis
**Task 3: Mission Outcome Distribution**
- **True ASDS:** Successful drone ship landings
- **True RTLS:** Successful ground pad landings
- **True Ocean:** Successful ocean landings
- **False ASDS:** Failed drone ship landings
- **False RTLS:** Failed ground pad landings
- **False Ocean:** Failed ocean landings
- **None None/None ASDS:** Complete landing failures

## Training Label Creation

### Binary Classification Logic
**Task 4: Landing Outcome Label Creation**

**Successful Landings (Class = 1):**
- True ASDS (successful drone ship)
- True RTLS (successful ground pad)
- True Ocean (successful ocean)

**Failed Landings (Class = 0):**
- None None (complete failure)
- False ASDS (failed drone ship)
- False Ocean (failed ocean)
- None ASDS (failed drone ship attempt)
- False RTLS (failed ground pad)

### Success Rate Calculation
- **Overall Success Rate:** Calculated using `df["Class"].mean()`
- **Binary Classification:** 1 = successful landing, 0 = unsuccessful landing

## Data Insights

### Launch Site Patterns
- **CCAFS SLC-40:** Primary launch facility with highest activity
- **VAFB SLC-4E:** Specialized for polar orbit launches
- **KSC LC-39A:** Used for specific mission types

### Orbit Type Insights
- **LEO:** Most frequent orbit type for various missions
- **GTO:** Common for commercial satellite deployments
- **ISS:** Regular resupply missions
- **Specialized Orbits:** SSO, VLEO for specific applications

### Landing Success Patterns
- **Success Rate:** Varies by landing method and mission type
- **Landing Methods:** ASDS (drone ship), RTLS (ground pad), Ocean
- **Failure Analysis:** Different failure modes identified

## Data Processing Results

### Final Dataset Structure
- **Total Records:** 90 launches
- **Target Variable:** Binary classification (Class: 0/1)
- **Features:** Launch site, orbit type, payload mass, etc.
- **Success Rate:** Calculated and validated

### Data Quality Improvements
- **Missing Values:** Identified and documented
- **Data Types:** Categorized as numerical vs categorical
- **Consistency:** Ensured uniform data formatting

## Key Findings Summary

### Launch Site Distribution
- CCAFS SLC-40: Dominant launch facility
- VAFB SLC-4E: Secondary facility
- KSC LC-39A: Third facility

### Orbit Type Distribution
- LEO: Most common orbit type
- GTO: Second most common
- ISS: Regular resupply missions
- Various specialized orbits identified

### Landing Success Analysis
- Multiple landing methods identified
- Success/failure patterns documented
- Binary classification labels created

## Output
- **CSV Export:** `dataset_part_2.csv` - Dataset with binary classification labels
- **Success Rate:** Calculated overall landing success rate
- **Training Labels:** Binary classification ready for machine learning

## Business Impact
- **Cost Implications:** Successful landings enable $62M vs $165M launch costs
- **Competitive Advantage:** Reusability is key to SpaceX's cost advantage
- **Prediction Value:** Binary classification enables cost prediction for competitors

This data wrangling phase established the foundation for machine learning by creating clear binary classification labels and providing insights into the factors that influence landing success rates.

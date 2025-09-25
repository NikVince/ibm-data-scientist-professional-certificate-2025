# SpaceX EDA with Visualization and Feature Engineering

**Reference:** `completed_assignements/10-05-spacex-eda-with-visualization.ipynb`

## Overview
This lab focused on performing comprehensive exploratory data analysis using visualization techniques and feature engineering to prepare the dataset for machine learning. The goal was to identify patterns, relationships, and prepare features for the landing prediction model.

## Key Objectives
- Perform exploratory data analysis with visualizations
- Identify relationships between variables and landing success
- Engineer features for machine learning
- Create dummy variables for categorical data

## Data Analysis Process

### Dataset Loading
- **Source:** `https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/datasets/dataset_part_2.csv`
- **Libraries:** pandas, numpy, matplotlib, seaborn
- **Initial Analysis:** 90 records with mixed data types

## Key Visualizations and Findings

### Task 1: Flight Number vs Launch Site
**Visualization:** `sns.catplot(x="FlightNumber", y="LaunchSite", hue="Class", data=df, aspect=5)`
- **Key Finding:** As flight number increases, success rate improves
- **Pattern:** Learning curve effect - later launches more successful
- **Launch Sites:** CCAFS SLC-40, VAFB SLC-4E, KSC LC-39A

### Task 2: Payload Mass vs Launch Site
**Visualization:** `sns.catplot(x="PayloadMass", y="LaunchSite", hue="Class", data=df, aspect=5)`
- **Key Finding:** VAFB SLC-4E has no heavy payload launches (>10,000 kg)
- **Pattern:** Launch site specialization by payload mass
- **Insight:** VAFB SLC-4E optimized for lighter payloads

### Task 3: Success Rate by Orbit Type
**Visualization:** `sns.barplot(x="Orbit", y="Class", data=orbit_success)`
- **Key Finding:** Different orbits have varying success rates
- **High Success Orbits:** LEO, ISS, VLEO
- **Lower Success Orbits:** GTO, SSO
- **Business Impact:** Orbit type affects landing success probability

### Task 4: Flight Number vs Orbit Type
**Visualization:** `sns.catplot(x="FlightNumber", y="Orbit", hue="Class", data=df, aspect=5)`
- **Key Finding:** LEO orbit shows clear success improvement over time
- **Pattern:** GTO orbit shows no clear relationship with flight number
- **Insight:** Learning curve varies by orbit type

### Task 5: Payload Mass vs Orbit Type
**Visualization:** `sns.catplot(x="PayloadMass", y="Orbit", hue="Class", data=df, aspect=5)`
- **Key Finding:** Heavy payloads show higher success rates for Polar, LEO, and ISS
- **Pattern:** GTO orbit difficult to distinguish success/failure
- **Insight:** Payload mass impact varies by orbit type

### Task 6: Yearly Success Trend
**Visualization:** `sns.lineplot(x="Year", y="Class", data=yearly, marker="o")`
- **Key Finding:** Success rate increased from 2013 to 2020
- **Pattern:** Continuous improvement in landing technology
- **Trend:** Steady upward trajectory in success rates

## Feature Engineering

### Selected Features
**Core Features:** `['FlightNumber', 'PayloadMass', 'Orbit', 'LaunchSite', 'Flights', 'GridFins', 'Reused', 'Legs', 'LandingPad', 'Block', 'ReusedCount', 'Serial']`

### Task 7: One-Hot Encoding
**Implementation:** `pd.get_dummies(features, columns=["Orbit", "LaunchSite", "LandingPad", "Serial"])`
- **Categorical Variables:** Orbit, LaunchSite, LandingPad, Serial
- **Result:** Expanded feature set with binary indicators
- **Purpose:** Prepare categorical data for machine learning

### Task 8: Data Type Conversion
**Implementation:** `features_one_hot.astype("float64")`
- **Purpose:** Ensure all features are numerical
- **Result:** Consistent data types for machine learning algorithms

## Key Insights from Visualizations

### Launch Site Patterns
- **CCAFS SLC-40:** Most active, handles various payload masses
- **VAFB SLC-4E:** Specialized for lighter payloads, no heavy launches
- **KSC LC-39A:** Third facility with mixed payload types

### Orbit Type Analysis
- **LEO:** High success rate, clear learning curve
- **GTO:** Lower success rate, no clear flight number relationship
- **ISS:** High success rate, regular resupply missions
- **Polar/SSO:** Moderate success rates

### Payload Mass Impact
- **Heavy Payloads:** Higher success rates for certain orbits
- **Light Payloads:** More variable success rates
- **Optimal Range:** Medium-heavy payloads show best success rates

### Temporal Trends
- **2013-2020:** Continuous improvement in success rates
- **Learning Curve:** Technology and experience improvements
- **Future Prediction:** Trend suggests continued improvement

## Feature Engineering Results

### Original Features (12)
- FlightNumber, PayloadMass, Orbit, LaunchSite, Flights, GridFins, Reused, Legs, LandingPad, Block, ReusedCount, Serial

### Expanded Features (After One-Hot Encoding)
- **Orbit Features:** Multiple binary indicators for each orbit type
- **LaunchSite Features:** Binary indicators for each launch site
- **LandingPad Features:** Binary indicators for landing pad types
- **Serial Features:** Binary indicators for core serial numbers

### Data Quality
- **All Numerical:** Converted to float64 for consistency
- **No Missing Values:** Clean dataset ready for machine learning
- **Standardized Format:** Consistent data structure

## Business Implications

### Cost Optimization
- **Success Rate Trends:** Improving landing success reduces costs
- **Orbit Selection:** Certain orbits have higher success rates
- **Payload Planning:** Optimal payload mass ranges identified

### Operational Insights
- **Launch Site Selection:** Site specialization by payload type
- **Mission Planning:** Orbit type affects success probability
- **Technology Evolution:** Continuous improvement in landing technology

## Output
- **CSV Export:** `dataset_part_3.csv` - Feature-engineered dataset
- **Visualizations:** 6 comprehensive plots showing key relationships
- **Feature Set:** Expanded from 12 to multiple binary features

## Technical Achievements
- **Comprehensive EDA:** Identified key patterns and relationships
- **Feature Engineering:** Prepared data for machine learning
- **Visualization:** Clear insights through graphical analysis
- **Data Preparation:** Clean, numerical dataset ready for modeling

This visualization and feature engineering phase provided crucial insights into the factors affecting landing success and prepared a comprehensive feature set for machine learning model development.

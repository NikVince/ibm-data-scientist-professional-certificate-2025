# SpaceX Data Collection via API

**Reference:** `completed_assignements/10-01-spacex-data-collection-api.ipynb`

## Overview
This lab focused on collecting SpaceX launch data through API requests and performing initial data wrangling to prepare the dataset for analysis. The goal was to predict if the Falcon 9 first stage will land successfully, which directly impacts launch costs (SpaceX: $62M vs competitors: $165M+).

## Key Objectives
- Request data from SpaceX API
- Clean and format the requested data
- Extract detailed information about rockets, payloads, launch sites, and cores

## Data Collection Process

### API Endpoint
- **Primary URL:** `https://api.spacexdata.com/v4/launches/past`
- **Static URL:** `https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/datasets/API_call_spacex_api.json`

### Data Extraction Functions
Created helper functions to extract detailed information:

1. **`getBoosterVersion()`** - Extracts booster name from rocket ID
2. **`getLaunchSite()`** - Gets launch site name, longitude, and latitude
3. **`getPayloadData()`** - Extracts payload mass and orbit information
4. **`getCoreData()`** - Comprehensive core data including:
   - Landing outcome and type
   - Number of flights
   - Grid fins usage
   - Reuse status
   - Landing pad information
   - Block version
   - Reuse count
   - Serial number

## Data Processing Results

### Initial Dataset
- **Total records:** 94 launches
- **Date range:** Up to November 13, 2020
- **Filtered:** Removed multi-core and multi-payload launches

### Data Quality Issues
- Missing values in `PayloadMass` column
- Missing values in `LandingPad` column (intentionally retained as None)

### Data Cleaning
- **PayloadMass:** Replaced NaN values with mean (calculated mean used for imputation)
- **FlightNumber:** Reset numbering after filtering to Falcon 9 launches only

## Final Dataset Structure
The processed dataset includes the following key features:
- **FlightNumber:** Sequential launch number
- **Date:** Launch date
- **BoosterVersion:** Falcon 9 variant
- **PayloadMass:** Mass of payload in kg
- **Orbit:** Target orbit type
- **LaunchSite:** Launch facility name
- **Outcome:** Landing outcome and type
- **Flights:** Number of flights for the core
- **GridFins:** Whether grid fins were used
- **Reused:** Whether core was reused
- **Legs:** Whether landing legs were used
- **LandingPad:** Landing pad used
- **Block:** Core block version
- **ReusedCount:** Number of times core was reused
- **Serial:** Core serial number
- **Longitude/Latitude:** Launch site coordinates

## Key Findings
- Successfully collected comprehensive launch data from SpaceX API
- Identified data quality issues and implemented appropriate cleaning strategies
- Created structured dataset with 94 Falcon 9 launches
- Established foundation for subsequent analysis phases

## Output
- **CSV Export:** `dataset_part_1.csv` - Cleaned dataset ready for next phase
- **Data Types:** Mixed numerical and categorical features identified
- **Missing Values:** Handled appropriately with mean imputation for PayloadMass

This initial data collection phase provided the foundation for the entire SpaceX landing prediction project, establishing a clean, structured dataset with comprehensive launch information.

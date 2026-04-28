# Spatial Analysis of Crime Patterns Across Gujarat State

This project analyzes district-wise crime patterns across Gujarat using spatial data analysis, exploratory mapping, and spatial regression techniques. The study combines crime statistics, district boundary data, and literacy information to identify spatial clustering, district trends, and the influence of neighboring districts on crime rates.

## Project Overview

The main objective of this project is to understand how crime is distributed across Gujarat and whether crime patterns show spatial dependence.

This notebook includes:

- Data preparation and cleaning
- Filtering Gujarat district-level crime data
- Creating crime rate per 100,000 population
- Mapping district-wise average crime rates
- Exploratory Spatial Data Analysis (ESDA)
- Moran’s I spatial autocorrelation analysis
- LISA-based hotspot analysis
- District-wise OLS regression
- Spatial Lag Model
- Spatial Error Model
- 2011 literacy-based spatial modeling

## Dataset Description

The analysis uses district-level crime data for Gujarat along with geospatial district boundaries. The filtered Gujarat GeoDataFrame contains **173 rows and 41 columns**, representing district-year level observations.

### Main Variables

- `DISTRICT` – Name of the district
- `CRIMEYEAR` – Year of recorded crime
- `CRIMETOTAL IPC CRIMES` – Total IPC crimes
- `CRIMEPOPULATION` – Population used to compute crime rate
- `CRIMERATEPER100K` – Crime rate per 100,000 population
- `geometry` – District boundary geometry
- `Literacy` – District literacy data for 2011 analysis

## Methods Used

### 1. Data Preparation
- Gujarat district boundaries were filtered from the larger geospatial dataset.
- District names were cleaned and standardized for merging.
- A population field was created to estimate district-wise crime rate per 100,000 people.

### 2. Exploratory Spatial Analysis
- District-level average crime rates were mapped using GeoPandas and Matplotlib.
- Choropleth maps were created to visualize variation in crime intensity across Gujarat districts.

### 3. Spatial Autocorrelation
- Global Moran’s I was used to test whether crime rates were spatially clustered.
- LISA analysis was used to identify district-level hotspots and coldspots.

### 4. Regression Analysis
- District-wise OLS regression was performed to study crime rate trends over time.
- A statewide OLS model was tested using crime year and population.
- Spatial Lag and Spatial Error models were then used to capture spatial dependence more effectively.

### 5. Literacy-Based Spatial Model
- For the year 2011, literacy data was merged with district crime data.
- Spatial regression models were tested to examine whether literacy explained crime-rate variation.

## Key Findings

### Spatial Pattern
Crime rates in Gujarat show clear spatial clustering rather than random distribution.

### Moran’s I Result
The overall residual-based spatial analysis showed positive spatial autocorrelation, indicating that nearby districts tend to have similar crime patterns.

### District Trends
Several districts showed declining crime trends over time, while a few districts displayed weak or increasing trends.

Examples from the notebook include:
- Anand showed a strong decreasing trend.
- Bharuch showed a significant decline.
- Junagadh showed a strong negative trend.
- Gandhinagar showed an increasing trend.
- Porbandar and Surendranagar showed strong decreasing trends.

### Model Performance
- The overall OLS model performed poorly for Gujarat.
- The Spatial Lag Model captured spatial dependence better than OLS.
- The Spatial Error Model was weaker in explaining the overall spatial structure.
- For 2011 literacy analysis, literacy was not consistently significant in explaining crime variation.

## Tools and Libraries Used

- Python
- Pandas
- GeoPandas
- NumPy
- Matplotlib
- Libpysal
- ESDA
- Spreg
- Jupyter Notebook / Google Colab

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/your-repo-name.git
   ```

2. Open the project folder:
   ```bash
   cd your-repo-name
   ```

3. Install required libraries:
   ```bash
   pip install pandas geopandas matplotlib numpy libpysal esda spreg
   ```

4. Open the notebook:
   ```bash
   jupyter notebook Spatial_Analysis_of_Crime_Patterns_across_GUJARAT_state.ipynb
   ```

## Learning Outcomes

This project helps in understanding:

- Spatial data preparation in Python
- Crime-rate normalization
- Geospatial visualization using district boundaries
- Spatial autocorrelation concepts such as Moran’s I
- Hotspot detection using LISA
- Difference between OLS and spatial regression models
- Practical use of GeoPandas and PySAL for GIS-based analysis

## Future Improvements

Possible future extensions include:

- Using real district-wise population instead of hypothetical estimates
- Including socio-economic variables beyond literacy
- Performing panel data or spatio-temporal analysis
- Building interactive web maps
- Comparing Gujarat with other Indian states

## Author

**Rudra M. Upadhyay**  

## License

This project is intended for academic, research, and learning purposes.

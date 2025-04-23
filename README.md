# Geographic Flight Delay Minutes Visualization Project

## Project Overview  
This project cleans and analyzes historical flight departure delay minutes in the month of January from 2018 to 2020. These large datasets are combined along with additional geographic coordinate data, and undergo extensive data cleaning before various plots, graphs, and visualizations are made for analysis. An interactive Folium-based visualization  maps and compares the daily average departure delays across U.S. airports, highlighting temporal patterns and geographic hotspots.

---

## Data Sources  
1. **Flight Delay Data**:  
   - Source: **“Flight Delay Dataset”** January 2018-2020 ([https://transtats.bts.gov/Fields.asp?gnoyr_VQ=FGK](https://www.kaggle.com/datasets/robikscube/flight-delay-dataset-20182022))  
   - Description: Three CSV files containing origin, destination, delay minute information and other necessary information.  

2. **Geographical Data**:  
   - Source: **Github Airport-codes Dataset** (([https://github.com/codeforgermany/click_that_hood/tree/main/public/data](https://www.kaggle.com/datasets/robikscube/flight-delay-dataset-20182022)])(https://github.com/datasets/airport-codes)  
   - Description: A CSV file with National and Internatinal airport geographical coordinates for mapping purposes.  
---

## Methods  
1. **Data Source & Preparation:**
- Utilized df_merged, which combines flight records from 2018–2020 with origin/destination coordinates.
- Calculated a per‐row average departure delay across the three years (avg_delay = mean(DepDelayMinutes_2018, DepDelayMinutes_2019, DepDelayMinutes_2020)).

2. **Aggregation:**
- Grouped by DayofMonth and OriginAirportID (plus latitude/longitude) to compute each airport’s mean avg_delay for every day 1–31.

3. **Map Construction:**
- Initialized a Folium map with CartoDB Positron tiles for a clean basemap.
- Created 31 mutually exclusive “base‐layer” FeatureGroups (Day 1 - Day 31), each displaying only that day’s airport markers.

4. **Visual Encoding:**
- Plotted each airport as a plane-icon marker, colored by delay bin:
    Green (<10 min), Yellow (10–15 min), Orange (15–20 min), Red (≥20 min).
- Added a simple HTML legend and a LayerControl with radio buttons so users can toggle to view exactly one day at a time.
 

---

## GitHub Pages  
The project, along with the Python scripts, data sources, and report documentation, is archived on a GitHub Page.  
**Link**: ([https://github.com/fflowerj/Flight-Delay-Visualization](https://github.com/annamariecobb/FlightDelayVisualization))

---

## Significance  
The interactive daily delay map is crucial because it reveals how systemic congestion, weather events, and infrastructure constraints vary not just over time but across the national network of airports with real historical data. By pinpointing which hubs and regions experience the worst departure delays on any given day, stakeholders–from airline operations teams to air‐traffic planners and travelers–can make more informed decisions about staffing, scheduling, and routing. Further, these insights support targeted investments in capacity, contingency planning for weather or peak‐travel surges, and ultimately, a smoother and more reliable air‐transport system for everyone.

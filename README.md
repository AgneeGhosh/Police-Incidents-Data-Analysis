# Police Incidents in San Francisco (2018–Present)

This project analyzes police incidents in San Francisco from 2018 to the present. Below is the step-by-step methodology implemented using R for data processing, visualization, and analysis. Each section of the code corresponds to a different aspect of the dataset. 

## 1. Data Import and Cleaning
Dataset: The dataset was loaded using read_csv().
Column Cleaning: Column names were standardized using clean_names() from the janitor package.
Datetime Formatting: Columns such as incident_datetime and report_datetime were converted to proper datetime formats using lubridate::ymd_hms(). The incident date was converted to a date format, and incident time was handled using hms().



## 2. Feature Engineering
Date Features: New features such as year, month, day of the week, and hour were extracted from the incident_datetime column using lubridate functions (year(), month(), wday(), hour()).
These additional features were useful in exploring temporal trends.

## 3. Yearly Trends Analysis
The dataset was grouped by year using group_by(incident_year), and the total number of incidents per year was calculated using summarize().
Visualization: A line plot was generated using ggplot2 to visualize trends in incident counts over time.

## 4. Geospatial Analysis
Spatial Data: For mapping incidents, leaflet was employed to create interactive maps showing the geographic distribution of incidents.
Neighborhood Analysis: Incident data was analyzed across various neighborhoods, and a heatmap was created using leaflet to highlight incident concentrations.

## 5. Incident Type and Time of Day Analysis
Incident Types: The data was grouped by incident types using dplyr::group_by() to calculate the frequency of each type of incident.
Visualization: A bar plot was created to visualize the distribution of incident types.
Time of Day: Incidents were analyzed by hour of the day to understand when incidents were most frequent.

## 6. Resolution Analysis
Resolutions of incidents (e.g., arrest, citation) were analyzed to examine the outcomes of incidents using summary functions like summarize().

This R-based workflow demonstrates a comprehensive methodology for cleaning, transforming, and analyzing police incident data in San Francisco. Key insights were derived from both temporal and spatial trends, which were further visualized using various R packages such as ggplot2 and leaflet.

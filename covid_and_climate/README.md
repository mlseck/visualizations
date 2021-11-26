# Covid & Climate

This visualisation shows potential relationships between the rise in COVID-19 infections and the current temperature per country (or state/province in North America).

## Visualization Rationale 

We chose to use a map because it allows to make a direct link between the temperature in a specific location and the evolution of cases throughout the year. The audience can easily look at the map and see if there seems to be a positive correlation between warmer temperatures and a decrease in cases in any country.

Here, we use color as a visual encoding to represent temperature; though color is not generally recommended for ordered visual encoding, we purposefully use it here because we are generally used to associating warmer weather with more red colors and cooler weather with blue colors. To avoid any confusion, we add the color scale as a legend on the visualization.The color scale is dynamic, and uses the lowest recorded temperature as its minimum value and the highest recorded temperature as its maximum value. We also add an interaction where the user can hover over a country, state or province to get more exact detail on the temperature, through text label encoding; this is considered redundant encoding.

To represent the number of cases per country, we use size (on top of placement on the map) as a visual encoding because it does a good job at representing quantitative data. Just to avoid any confusion with regards to scale, we also use text labeling, on top of size, to convey the rise in cases.

Another interaction on this map consists of changing between different months of the year to see how temperature will differ and the impact it may have on the rise or fall in cases.

## Methodology

The visualization uses color to show monthly temperature averages for each country, and in the case of the US and Canada, for each state and province. As the interaction element, the user can navigate the months of 2020 and see how the temperature changes through them. On top of the temperature changes, the visualization uses shape and radius to mark the percentage rise in COVID cases compared to the previous month. As such, the visualisation allows for the user to see whether there is a trend between temperature change and rise or fall in COVID cases in different parts of the world.

In order to implement this visualization, the following data sources were used:

- [**Monthly temperature averages](https://github.com/marichig/weather-conditions-COVID19/blob/master/WeatherDataCollection/data/MasterDoc_V6.1.xlsx) for 2020 by country in the world**
    - Source: Johns Hopkins University Center for Systems Science and Engineering
- [**Daily temperatures by station](https://www.ncdc.noaa.gov/cag/statewide/mapping/110/tmax/202002/1/value) in the US**
    - Processing done:
        - Cleaning and averaging out temperature by state and by month
    - Source: National Centers for Environmental Information
- [**Daily temperatures by station](https://climate.weather.gc.ca/prods_servs/cdn_climate_summary_e.html) in Canada**
    - Processing done:
        - Cleaning and averaging out temperature by state and by month
    - Source: Government of Canada Weather, Climate and Hazard unit
- **Daily confirmed COVID cases per country**
    - Processing done:
        - Aggregated data by country and month
        - Computed monthly rise in COVID cases per country
    - Source: Provided on Keats
- [**Daily confirmed COVID cases per state in the US**](https://github.com/nytimes/covid-19-data/blob/master/us-states.csv)
    - Processing done:
        - Aggregated data by state and month
        - Computed monthly rise in COVID cases per state
    - Source: New York Times
- [**Daily confirmed COVID cases per province in Canada**](https://github.com/ccodwg/Covid19Canada)
    - Processing done:
        - Aggregated data by province and month
        - Computed monthly rise in COVID cases per province
    - Source: COVID-19 Canada Open Data Working Group

The Jupyter Notebook in this repo the cleaning and processing steps that were carried out on the various datasets. All clean datasets have been uploaded in JSON format on this [Github repository](https://github.com/mlseck/datasets).

The following Github repository was also used to help  get a D3 map with all countries in the world, all US states and all Canadian provinces: [d3 map with states and countries](https://gist.github.com/MaciejKus/61e9ff1591355b00c1c1caf31e76a668).


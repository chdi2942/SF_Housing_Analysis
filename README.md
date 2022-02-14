# SF_Housing_Analysis

## Housing Rental Analysis for San Francisco

In this program, we will use including data aggregation, interactive visualizations, and geospatial analysis, to find properties in the San Francisco market that are viable investment opportunities.

### Overview

We will use the `san_francisco_housing.ipynb` notebook to visualize and analyze the real-estate data.

Additionally we will complete the following tasks:

* Calculate and plot the housing units per year.

* Calculate and plot the average prices per square foot.

* Compare the average prices by neighborhood.

* Build an interactive neighborhood map.

* Compose our data story.

#### Calculate and Plot the Housing Units per Year

We will use numerical and visual aggregation to calculate the number of housing units per year, and then visualize the results as a bar chart. To do so, we will:

1. Use the `groupby` function to group the data by year. Aggregate the results by the `mean` of the groups.

2. Use the `hvplot` function to plot the `housing_units_by_year` DataFrame as a bar chart. Make the x-axis represent the `year` and the y-axis represent the `housing_units`.

3. Style and format the line plot to ensure readability.

4. Answer the following question:

    * What’s the overall trend in housing units over the period being analyzed?

#### Calculate and Plot the Average Sale Prices per Square Foot

In this section, we will use numerical and visual aggregation to calculate the average prices per square foot, and then visualize the results as a bar chart. To do so, we will:

1. Group the data by year, and then average the results. We will answer what the lowest gross rent that’s reported for the years that the DataFrame includes.

2. Create a new DataFrame named `prices_square_foot_by_year` by filtering out the “housing_units” column. The new DataFrame will include the averages per year for only the sale price per square foot and the gross rent.

3. Use hvPlot to plot the `prices_square_foot_by_year` DataFrame as a line plot.

4. Style and format the line plot to ensure a readable visualization.

5. Use both the `prices_square_foot_by_year` DataFrame and interactive plots to answer the following questions:

    * Did any year experience a drop in the average sale price per square foot compared to the previous year?

    * If so, did the gross rent increase or decrease during that year?

#### Compare the Average Sale Prices by Neighborhood

For this section, we will use interactive visualizations and widgets to explore the average sale price per square foot by neighborhood. To do so, we will:

1. Create a new DataFrame that groups the original DataFrame by year and neighborhood. Aggregate the results by the `mean` of the groups.

2. Filter out the “housing_units” column to create a DataFrame that includes only the `sale_price_sqr_foot` and `gross_rent` averages per year.

3. Create an interactive line plot with hvPlot that visualizes both `sale_price_sqr_foot` and `gross_rent`. Set the x-axis parameter to the year (`x="year"`). Use the `groupby` parameter to create an interactive widget for `neighborhood`.

4. Style and format the line plot to ensure a readability.

5. Use the interactive visualization to answer the following question:

    * For the Anza Vista neighborhood, is the average sale price per square foot for 2016 more or less than the price that’s listed for 2012? 

#### Build an Interactive Neighborhood Map

For this section, we will explore the geospatial relationships in the data by using interactive visualizations with hvPlot and GeoViews. To build our map, we will use the `sfo_data_df` DataFrame (created during the initial import), which includes the neighborhood location data with the average prices. To do all this, we will:

1. Read the `neighborhoods_coordinates.csv` file from the `Resources` folder into the notebook, and create a DataFrame named `neighborhood_locations_df`, settomg the `index_col` of the DataFrame as “Neighborhood”.

2. Using the original `sfo_data_df` Dataframe, create a DataFrame named `all_neighborhood_info_df` that groups the data by neighborhood. Aggregate the results by the `mean` of the group.

3. Review the two code cells that concatenate the `neighborhood_locations_df` DataFrame with the `all_neighborhood_info_df` DataFrame. Note that the first cell uses the [Pandas concat function] to create a DataFrame named `all_neighborhoods_df`. The second cell cleans the data and sets the “Neighborhood” column.  We'll run these cells to create the `all_neighborhoods_df` DataFrame, which we’ll need to create the geospatial visualization.

4. Using hvPlot with GeoViews enabled, create a `points` plot for the `all_neighborhoods_df` DataFrame. We will achieve this by:

    * Set the `geo` parameter to True.
    * Set the `size` parameter to “sale_price_sqr_foot”.
    * Set the `color` parameter to “gross_rent”.
    * Set the `frame_width` parameter to 700.
    * Set the `frame_height` parameter to 500.
    * Include a descriptive title.


5. Use the interactive map to answer the following question:

    * Which neighborhood has the highest gross rent, and which has the highest sale price per square foot?

#### Compose The Data Story

Based on the visualizations that you created:

* How does the trend in rental income growth compare to the trend in sales prices? Does this same trend hold true for all the neighborhoods across San Francisco?

* What insights can you share with your company about the potential one-click, buy-and-rent strategy that they're pursuing? Do neighborhoods exist that you would suggest for investment, and why?

### Conclusion 

**Question:**  How does the trend in rental income growth compare to the trend in sales prices? Does this same trend hold true for all the neighborhoods across San Francisco?

**Answer:** Based on the visualizations that we have created, it is clear that rental income has grown more quickly and consistantly than sales prices in San Francisco from 2010 to 2016.  This is true for every neighboorhood across San Francisco, including Union Square Park, which despite a significant increase in sales price during the period, still had rent growth that outpaced this growth in sales price.

**Question:** What insights can we share about a potential one-click, buy-and-rent strategy? Do neighborhoods exist that you would suggest for investment, and why?

**Answer:** Although there are many ways you can approach answering this question, according to the data between 2010 and 2016, I would recommend in favor of the one-click, buy-and-rent strategy.  This is because the price that you would pay for the home is not increasing as much as the income that would be generated renting out the property, so you could get homes that have increasing passive income for "relatively" cheap.  When analyzing which neighborhoods to buy from, I would suggest looking for neighborhoods with cheaper/(stable or increasing) sale prices and higher/increasing rent prices.  This is because there would be a lower initial cost of the sale, you would expect to eventually sell the property for more than you bought it for, and you would expect your passive income from the property (rent) to increase over time.  These neighborhoods that I like include Central Richmond, Central Sunset, Croker Amazon, Downtown, Excelsior, Glen Park, Haight Ashbury, Inner Mission, Nob Hill, Parnassus/Ashbury Heights, Russain Hill, Sunnyside, and Twin Peaks

### Requirements
* Python 3.7
* Jupyter Lab
* Pandas library
* HV Plot
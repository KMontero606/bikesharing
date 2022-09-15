# bikesharing

## Overview of Project:
There is still some more work to be done to convince investors that a bike-sharing program in Des Moines is a solid business proposal. To solidify the proposal, one of the key stakeholders would like to see a bike trip analysis.

For this analysis, use Pandas to change the "tripduration" column from an integer to a datetime datatype. Then, using the converted datatype, create a set of visualizations to:

* Show the length of time that bikes are checked out for all riders and genders
* Show the number of bike trips for all riders and genders for each hour of each day of the week
* Show the number of bike trips for each type of user and gender for each day of the week.

Finally, add these new visualizations to the two already created for the final presentation and analysis to pitch to investors.

## Results:
### Deliverable 1: Change Trip Duration to a Datetime Format
```
Deliverable 1: Change Trip Duration to a Datetime Format
import pandas as pd

# 1. Create a DataFrame for the 201908-citibike-tripdata data. 
citibike_df = pd.read_csv("201908-citibike-tripdata.csv")

# 2. Check the datatypes of your columns. 
citibike_df.dtypes

# 3. Convert the 'tripduration' column to datetime datatype.
citibike_df['tripduration'] = pd.to_datetime(citibike_df['tripduration'], unit='s')

# 4. Check the datatypes of your columns. 
citibike_df

# 5. Export the Dataframe as a new CSV file without the index.
citibike_df.to_csv("201908-citibike-tripdata_2.csv", index = False)
```

### Deliverable 2: Create Visualizations for the Trip Analysis

### Deliverable 3: Create a Story and Report for the Final Presentation
https://public.tableau.com/shared/RDW86ZNPX?:display_count=n&:origin=viz_share_link

## Summary:

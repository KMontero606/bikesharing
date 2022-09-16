# bikesharing

## Overview of Project:
There is still some more work to be done to convince investors that a bike-sharing program in Des Moines is a solid business proposal. One of the key stakeholders would like to see a bike trip analysis in order to solidify the proposal.

For this analysis, Pandas was used to modify the dataset procured from NYC CitiBike for the month of August. Then, the converted datatype was utilized to create a set of visualizations to:

* Show the length of time that bikes are checked out for all riders and genders
* Show the number of bike trips for all riders and genders for each hour of each day of the week
* Show the number of bike trips for each type of user and gender for each day of the week.

Finally, these visualizations along with two others were created for the final presentation and analysis to pitch to investors.

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
#1. Create the Checkout Times for Users Viz:
<img width="946" alt="Checkout Times for Users" src="https://user-images.githubusercontent.com/106962921/190651621-0c5860ce-0eca-40af-b492-4b572d42ca5c.png">

How long bikes are checked out for all riders. It is observed that a bike is checked out for no more than one hour.

#2. How long bikes are checked out for all riders:
<img width="950" alt="Checkout Times by Genders" src="https://user-images.githubusercontent.com/106962921/190651992-66488eda-94a4-40a2-9090-907f255e68fb.png">

How long bikes are checked out for all genders. The most common users are male.

#3. Create the Trips by Weekday for Each Hour Viz:
<img width="948" alt="Trips by Weekday per Hour" src="https://user-images.githubusercontent.com/106962921/190652202-1d845435-531c-4e11-b0ce-9bc51461ecd6.png">

How many trips are taken by the hour for each day of the week for all riders. Monday, Tuesday, Thursday and Friday are the most trips taken during the morning and late afternoon.

#4. Create the Trips by Gender (Weekday per Hour) Viz:
<img width="950" alt="Trips by Gender" src="https://user-images.githubusercontent.com/106962921/190652666-969b041e-4fcd-4eb5-9df0-208d4ce4840c.png">
How many trips are taken by the hour for each day of the week for all genders. The most common trips taken are from the male population.

#5. Create the User Trips by Gender by Weekday Viz:
<img width="949" alt="User Trips Gender Weekday" src="https://user-images.githubusercontent.com/106962921/190652957-028a99c1-daac-4e35-994b-d49987a7faf6.png">

A breakdown of what days of the week a user might be more likely to check out a bike, by type of user and gender. Male Subscribers are more likely to check out a bike at the beginning and end of the week. 

### Deliverable 3: Create a Story and Report for the Final Presentation
The CitiBike story was built using [Tableau Pages](https://public.tableau.com/app/profile/karen.montero/viz/NYC_CitiBike_Challenge_16630730954770/NYCCitiBikeforAugust2019).

## Summary:

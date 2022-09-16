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

tripduration                 int64
starttime                   object
stoptime                    object
start station id           float64
start station name          object
start station latitude     float64
start station longitude    float64
end station id             float64
end station name            object
end station latitude       float64
end station longitude      float64
bikeid                       int64
usertype                    object
birth year                   int64
gender                       int64
dtype: object

# 3. Convert the 'tripduration' column to datetime datatype.
citibike_df['tripduration'] = pd.to_datetime(citibike_df['tripduration'], unit='s')

# 4. Check the datatypes of your columns. 
citibike_df

	tripduration	starttime	stoptime	start station id	start station name	start station latitude	start station longitude	end station id	end station name	end station latitude	end station longitude	bikeid	usertype	birth year	gender
0	1970-01-01 00:06:33	2019-08-01 00:00:01.4680	2019-08-01 00:06:35.3780	531.0	Forsyth St & Broome St	40.718939	-73.992663	408.0	Market St & Cherry St	40.710762	-73.994004	35305	Subscriber	1996	2
1	1970-01-01 00:10:27	2019-08-01 00:00:01.9290	2019-08-01 00:10:29.7840	274.0	Lafayette Ave & Fort Greene Pl	40.686919	-73.976682	3409.0	Bergen St & Smith St	40.686744	-73.990632	38822	Subscriber	1998	2
2	1970-01-01 00:18:52	2019-08-01 00:00:04.0480	2019-08-01 00:18:56.1650	2000.0	Front St & Washington St	40.702551	-73.989402	3388.0	President St & Henry St	40.682800	-73.999904	18373	Subscriber	1988	1
3	1970-01-01 00:29:40	2019-08-01 00:00:04.1630	2019-08-01 00:29:44.7940	479.0	9 Ave & W 45 St	40.760193	-73.991255	473.0	Rivington St & Chrystie St	40.721101	-73.991925	25002	Subscriber	1988	1
4	1970-01-01 00:25:17	2019-08-01 00:00:05.4580	2019-08-01 00:25:23.4550	3312.0	1 Ave & E 94 St	40.781721	-73.945940	3312.0	1 Ave & E 94 St	40.781721	-73.945940	31198	Subscriber	1965	2
...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...
2344219	1970-01-01 00:03:36	2019-08-31 23:59:46.2930	2019-09-01 00:03:23.0360	116.0	W 17 St & 8 Ave	40.741776	-74.001497	509.0	9 Ave & W 22 St	40.745497	-74.001971	38655	Subscriber	1972	1
2344220	1970-01-01 00:01:57	2019-08-31 23:59:47.7970	2019-09-01 00:01:45.7440	3429.0	Hanson Pl & Ashland Pl	40.685068	-73.977908	353.0	S Portland Ave & Hanson Pl	40.685396	-73.974315	25264	Subscriber	1982	2
2344221	1970-01-01 00:26:54	2019-08-31 23:59:48.1560	2019-09-01 00:26:42.7760	387.0	Centre St & Chambers St	40.712733	-74.004607	3440.0	Fulton St & Adams St	40.692418	-73.989495	28485	Customer	1969	0
2344222	1970-01-01 00:21:41	2019-08-31 23:59:58.3620	2019-09-01 00:21:39.7040	3168.0	Central Park West & W 85 St	40.784727	-73.969617	423.0	W 54 St & 9 Ave	40.765849	-73.986905	38664	Customer	1969	0
2344223	1970-01-01 00:06:59	2019-08-31 23:59:59.4520	2019-09-01 00:06:59.0210	447.0	8 Ave & W 52 St	40.763707	-73.985162	529.0	W 42 St & 8 Ave	40.757570	-73.990985	35210	Subscriber	1994	1

2344224 rows × 15 columns

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
The NYC CitiBike story was built using [Tableau Public](https://public.tableau.com/app/profile/karen.montero/viz/NYC_CitiBike_Challenge_16630730954770/NYCCitiBikeforAugust2019#2).

## Summary:
There are over 2 million trips taken that utilizes the CitiBike service in the month of August, a perfect weather condition for bike riding. With the number of bike users, majority are from men than women although there are a number of unknown users who may not want to identify with either gender. There are more trips taken in the late afternoon than in the morning for no more than an hour during Monday, Tuesday and more heavily on Thursday than Friday given that Friday would be more ideal since it is the beginning of the weekend. The male population are more likely to go on more trips than the female population and male subscribers account for majority of the users of the CitiBike service. Over the course of these trips, one must take into account bike repairs to ensure the safety of our users as well as longevity of the bikes.

Additional visualization can be performed for future analysis. One such analysis would be at what age group do bike users fall into that utilizes the CitiBike service. With this information, we can determine if different sizes of bikes, types of bikes, are needed to accomodate certain age group i.e. for family with children going on bike rides together or riders who partake in marathon.

Another analysis that would be helpful would be 


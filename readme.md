# Predicting Demand and Location for Air-Taxi Operations

![Title](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Images/eVTOL-Los-Angeles.jpg)

### Overview

Science fiction turned science fact, air taxis are closer than we think. With the heavy adoption of electric vehicles by the automotive industry, and advancements in battery technology, companies are finally able to produce electronic VTOL aircrafts that can be used for daily air travel.

E-VTOLs create a whole new form of transportation, allowing for faster air-travel in-between cities, towns and major service locations. The lower operating cost, lower noise and zero-carbon emission of the eVTOLs will allow service to be more frequent, available in many locations across the city and finally establish itself as a major form of transportation in the times to come. 

### Understanding the Problem

1. The demand for road travel exceeds the supply given how fast urban populations are growing. The capital intensive and time consuming nature of new roadway/public transit, 
   makes it almost impossible for most cities to meet the growing demand for travel.
2. According to a recent study, U.S. drivers **lost an average of 99 hours** in traffic equivalent to **$1,377** in 2019 due to traffic congestions. ($88 billion in national average)
3. Move to a greener future. 


### Project Objectives:

- Explore FasTrak data to analyze traffic movement and density in the Bay Area.
- Find traffic hotspots to serve as air-taxi hubs.
- Analyze transportation needs at each location.
- Recommend optimal location, service routes and hours of operations for air-taxi service.


### Data:

- FasTrak is an automatic toll collection system in the Bay Area. The data provided has daily and hourly volumes of traffic flow with locations of each toll. 
We will assume observed traffic movements as an indicator of demand at each location. Using the geo-coordinates of each toll, we will narrow down to some key locations 
that will act as our Air-taxi hubs providing the most optimal means of transport.

-----------------------------------------------------------------------------------------------------------------

### Base map

We will use Google Maps API to plot all our required locations. Using some simple code, we are able to plot FasTrak locations with daily volumes of traffic observed at each location.

![Density Blob](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Images/density_blob.png)

Blob scale is between (1 - 20) representing daily traffic volume between (20,000 - 400,000) approx.

-----------------------------------------------------------------------------------------------------------------

### Total Daily Flow of Traffic

![Daily](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/Total%20Daily%20Traffic%20Volume.png)

Looking at the above graph, there are some clear trends in the daily flow of traffic.
- Daily traffic shows an increasing trend Monday through Friday.
- There is a sharp decrease in traffic during the weekends.


### Total Hourly Flow of Traffic

![Hourly](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/Hourly%20Traffic%20Volume.png)

Similar to the previous graph, there are some clear trends in the hourly flow of traffic.
- Traffic starts from 5 am in the morning. 
- There is an average traffic of over 1000 per hour throughout the day.
- Traffic begins to fall off from 5 pm the evening until midnight.


### Directional Flow of Traffic

![Directional](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/Directional.png)

We can see that there is higher movement of traffic in either West or East directions. San Francisco being the central location of our analysis, 
we can note that most of these volumes seen could be from traffic moving in and out of the city. However, we will have to look into a 
bit deeper to figure out the exact location and direction where the traffic density is the highest.

-----------------------------------------------------------------------------------------------------------------

### Location Modelling

Using K-Means clustering algorithm we are able to narrow down to 10 optimal clusters that serve over 230,000 travellers across all directions.

![Cluster](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/clusters.png)

Combining locations at each cluster, we arrive at 10 separate locations where we will set up our final air taxi hubs.

![hubs](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/hubs.png)

-----------------------------------------------------------------------------------------------------------------

### Service Routes

Looking at routes that take more than 8 minutes of flight time, we have the following combination of trips.

![Routes](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/routes.png)

- Red: Southbound
- Blue: Northbound
- Green: Westbound
- Black: Eastbound

Having flight time over 8 minutes will allow our air taxis to cover larger distances and make the trip worth while.


### Air Taxi vs Conventional Travel

![Speed](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/time_comparision.png)

The above line graphs represents time taken to travel each of the planned service routes. It is pretty evident that the sample aircrafts are atleast 3-4 times faster than driving.

-----------------------------------------------------------------------------------------------------------------

### Predicting demand on each of those routes

Assuming that only 10% of the total traffic opts to use our air taxi service, the daily demand estimate still comes out to an average of over 45,000 at each location.
For an 18 hour operating period, we can expect an hourly demand of more than 2500 for our air-taxi service.

![Demand](https://github.com/dicchyant84/Air-Taxi-Logistics/blob/main/Graphs/demand.png)

-----------------------------------------------------------------------------------------------------------------

### Conclusion/Recommendation

- On an average there seems to be an hourly demand of above 2500 customers at all locations. This only represents 10% of the total flow of traffic daily.
- Considering most of the travel is happening during morning and evening rush hours, an operating schedule between the hours of 6 AM till 12 AM would benefit the most travellers.
- In terms of service locations, we identified a total of 10 locations that would be optimal to cover all movements across the area.
- Considering all combination of travel between these locations, and keeping only the routes that take at least 8 minutes of flight time, we arrive at 15 different routes that will benefit the most from this service.
- Each of these routes are at least 4 times faster than conventional travel.

By looking at just the Fastrak data, we are able to identify the most optimal locations, routes that covers the most distance and forecast an average demand of 50,000 travellers 
everyday. Regardless of what air taxi we choose or follow a certain pricing plan, it is pretty evident that there will be more than enough demand for this service. The travel being more than 3-4 times faster will also make this service invaluable at all price ranges. 
This is a great opportunity and investors should definitely take part to make this a success.




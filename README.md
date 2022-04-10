# w205-caltrain-final
Final project group work (Vineeta, Landon, Evan)

Acme Gourmet Meals (AGM) is exploring new delivery options to expand to new customers in the Bay Area. There is interest in the options below:

 - Adding more pickup locations
 - Using public transportation to transport deliveries
 - Using delivery drones
 - Using delivery robots
 - A hybrid approach of any combination of these options
 
 By using the Berkley store as a hub and the Bay Area Rapid Transit System in addition to the other options above, we will look into the most effective way to expand and service the largest number of new customers.
 
 # Data Cleansing and Analysis
 3_1: Create and load data into SQL relational tables
 
 3_2: SQL queries for transit data
 
 3_3: Create a graph database in Neo4J
 
 3_4: Verify and explore graph database for transit data
 
 3_5: Use Geodesic distances to explore models of expanding deliveries using BART public transit
 
 bay_area_population_exploration: Create functions to identify new customers and their nearest stations 
 
 transit_code: Create interactive maps for exploration of new delivery options in the Bay Area's most populous areas
 
 # Files
 Lines: CSV containing BART lines and affiliated stations
 
 Stations: CSV containing stations and their geolocation
 
 Travel_Times: CSV containing travel times to and from stations on the BART system
 
 transit: GEOJSON from 511.org transit database containing station locations, names, and coordinates of connecting lines
 
 stroke: GEOJSON cleaned and only containing information to create transit lines
 
 
 # Background
 Berkeley is the highest grossing store in the AGM chain and has potential for even more expansion in the Bay Area. Right now, other than a small pilot with a delivery company that ate into our margins, the only way for our customers to get food is to pick it up from our Berkeley location. Instead of a new store location in a competitive real-estate market like the Bay Area, AGM will look to expand by offering additional pickup and delivery services using a combination of BART and emerging high-tech delivery options via drone or robot. 
 
 Key Objectives to expansion:
 - Do not canabalize our current business. If we offer delivery to the same loyal customers that already come into the store we will reduce our magin without growing.
 - Make it easier for low frequency customers to purchase who may be too far away to come into the store often.
 - Introduce our products to new customers who cannot come into the store simple because it's too far away.
 
 In this analysis we considered the following options:
 - Adding more pickup locations
 - Using public transportation to transport food
 - The use of flying delivery drones
 - Using delivery robots
 - A hybrid approach of all of the above
 
 
 # Analysis & Strategy for Expansion
 Current situation
 - The Berkeley AGM location had $25mm in revenue with an average order value of $64
 - Customers: 8,100
 - Orders: 390k
 - The majroity of customers are concentrated around the Berkely store.
     - On average a customer traveled 7.5 miles to come to the store
 
To expand our business, we specifically need to reach a broader customer base than who we are currently serving. 

A cost effective way to reach a broader audience is to capitalize on Bay Area public infrastructures such as BART, coupled with new delivery options such as drones or robots.

A quick overlay of the BART lines showcases the potential service areas that can be reached via the BART routes.

We also evaluated all the zip codes along the BART route and identified areas where we have at least 75% new target customers within an 8 mile radius. 

Based on the above methodology, our target areas for new customers are concentrated near the following cities:
- San Francisco
- Daly City 
- South Bay/San Jose
- Union City/Fremont

Of the four locations identified, we recommend the following cities for the POC along with the proposed delivery strategies

Daly City (A)
- We recommend setting up a pick up location in Daly City 
- A delivery person will pick up orders from the Berkeley store and commute ~40 minutes to the pop up location near the Daly City station. 
- Both Daly City and San Francisco are heavily populated cities with a large target overlap. Setting up a pick up location in Daly City will enable us to tap into both markets (SF - density 18.6k/mi^2; Daly City - density 13.6/mi^2)
- We should also set up marketing banners in front of the terminal to increase brand awareness

San Jose (B)
- We recommend a combination of delivery person and drone for San Jose 
- With a density of 5.6k/mi^2, San Jose is a viable option to test drone deliveries
- A delivery person will pick up orders and commute ~2hrs to San Jose, after which a delivery drone can fly out within a radius of 8 miles to deliver under ~7 minutes


# Revenue Analysis
Key Assumptions: 
- ~20% base penetration of customers similar to current customer penetration across Berkeley service zip codes
- Customers will order 5 meals per order similar to a typical AGM customer
- customers will buy 4.13 times per month
- The POC will be run for 30 days

Potential new customers in each location:
- Berryessa: 1,181,963
- Daly City: 1,108,404
- Antioch: 325,681
- Dublin: 374,831
Total: 2,990,879

Potential pilot revenue:
- Base: $493,748.87
- Bear: $370,311.66
- Bull: $61,7186.09
 
 
# Infrastructure Considerations
The POC success is also dependant on the right infrastructure which allows us to be nimble, cost effective and scalable

Requirements:
- Flexibility: ability to maintain relationships between stations, transit times, flying time
- Expansion: Ability to add mroe data as we explore innovative solutions
- Performance
- Scalability
- Upfront Cost

We recommend using neo4j to create maps and track delivery times across transit and dones. We also recommend MongoDB for a scalable schema.

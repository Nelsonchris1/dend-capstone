# Udacity Data Engineering Capstone Project

# Temperature the biggest reason for immigration or just random event?

## Project summary

Data analyist in Our company have been given to task to see if the temperature of a place has been the biggest factor of immigration or it might just have been a random event. Data analysts have approached data engineer to provide them clean data to aid thier analysis. I94 Immigration data and city temperature data will be used to create a database that is optimized to query and analyze immigration events. An ETL pipeline is to be build with these to data sources to create the database. After much debate between the data engineering team in collaboration with the data analyst , based on the requirements, We'll be creating a start schema table with 2 dimension tables and 1 fact table. we will aggregate I94 immigration data by destination city to form our first dimension table,next we will aggregate city temperature data by city to form the second dimension table. The two datasets will be joined on destination city as primary key to form the fact table. The final database is optimized to query on immigration events to determine if temperature affects the selection of destination cities. Spark will be used to process the data.


## * Scope the Project and Gather Data
______________________________________________________________
**The I94 immigration data comes from the US National Tourism and Trade Office**
- i94yr = 4 digit year,
- i94mon = numeric month,
- i94cit = 3 digit code of origin city,
- i94port = 3 character code of destination USA city,
- arrdate = arrival date in the USA,
- i94mode = 1 digit travel code,
- depdate = departure date from the USA,
- i94visa = reason for immigration,

**The temperature data is a Kaggle data set**
- AverageTemperature = average temperature,
- City = city name,
- Country = country name,
- Latitude= latitude,
- Longitude = longitude

## Final Data model
**Fact Table** - I94 immigration data joined with the city temperature data on i94port
Columns:
   - i94yr = 4 digit year,
   - i94mon = numeric month,
   - i94cit = 3 digit code of origin city,
   - i94port = 3 character code of destination USA city,
   - arrdate = arrival date in the USA,
   - i94mode = 1 digit travel code,
   - depdate = departure date from the USA,
   - i94visa = reason for immigration,
   - AverageTemperature = average temperature of destination city,

**Dimension Table** - I94 immigration data Events
Columns:
   - i94yr = 4 digit year
   - i94mon = numeric month
   - i94cit = 3 digit code of origin city
   - i94port = 3 character code of destination USA city
   - arrdate = arrival date in the USA
   - i94mode = 1 digit travel code
   - depdate = departure date from the USA
   - i94visa = reason for immigration

**Dimension Table** - temperature data
Columns:
- i94port = 3 character code of destination city (mapped from cleaned up immigration data)
- AverageTemperature = average temperature
- City = city name
- Country = country name
- Latitude= latitude
- Longitude = longitude

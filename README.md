# Data602_finalproject

### Data Source :
https://data.cityofnewyork.us/Housing-Development/Housing-New-York-Units-by-Building/hg8x-zxpr

### Project Description :

This dataset represents Newyork housing datasets where each row indicates a project and its status based on the number of bed rooms(1-BR, 2-BR, 3_BR,...,6BR+ units) and location.

### Project Proposal :

Based on the multiple features like number of bed rooms, income levels, latitude, longitude, project completion date etc. predicting the total units that will be produced.

### Feature description :

- Project ID :The Project ID is a unique numeric identifier assigned to each project by HPD.
- Project Name : The Project Name is the name assigned to the project by HPD.
- Project Start Date : The Project Start Date is the date of the project loan or agreement closing.
- Project Completion Date : The Project Completion Date is the date that the last building in the project was completed. If the project has not yet completed, then the field is blank.
- Building ID : The Building ID is a unique numeric identifier assigned to each building by HPD.
- Number : The House Number is the street number in the building’s address. E.g., the house number is ‘100’ in ‘100 Gold Street.’
- Street : The Street Name is the name of the street in the building’s address. E.g., the street name is ‘Gold Street’ in ‘100 Gold Street.’
- Borough :The Borough is the borough where the building is located.
- Postcode : Zip code
- BBL : The BBL (Borough, Block, and Lot) is a unique identifier for each tax lot in the City.
- BIN :The BIN (Building Identification Number) is a unique identifier for each building in the City.
- Community Board : The Community Board field indicates the New York City Community District where the building is located.
- Council District : The Council District indicates the New York City Council District where the building is located.
- Census Tract : The Census Tract indicates the 2010 U.S. Census Tract where the building is located.
- NTA - Neighborhood Tabulation Area : The Neighborhood Tabulation Area indicates the New York City Neighborhood Tabulation Area where the building is located.
- Latitude : The Latitude and Longitude specify the location of the property on the earth’s surface. The coordinates provided are an estimate of the location based on the street segment and address range.
- Longitude : The Latitude (Internal) and Longitude (Internal) specify the location of the property on the earth’s surface. The coordinates provided are of the internal centroid derived from the tax lot.
- Building Completion Date : The Building Completion Date is the date the building was completed. The field is blank if the building has not completed.
- Reporting Construction Type : The Reporting Construction Type field indicates whether the building is categorized as ‘new construction’ or ‘preservation’ in Housing New York statistics. Note that some preservation projects included here may not actually involve construction, because they extend the project’s regulatory restrictions but do not require rehabilitation.
- Extended Affordability Only : The Extended Affordability Only field indicates whether the project is considered to be Extended Affordability. An extended affordability project involves no construction, but secures an extended or new regulatory agreement. All extended affordability projects have a ‘reporting construction type’ of ‘preservation.’
- Prevailing Wage Status : The Prevailing Wage Status field indicates whether the project is subject to prevailing wage requirements, such as Davis Bacon.
- Extremely Low Income Units : Extremely Low Income Units are units with rents that are affordable to households earning 0 to 30% of the area median income (AMI).
- Very Low Income Units : Very Low Income Units are units with rents that are affordable to households earning 31 to 50% of the area median income (AMI).
- Low Income Units : Low Income Units are units with rents that are affordable to households earning 51 to 80% of the area median income (AMI).
- Moderate Income Units : Moderate Income Units are units with rents that are affordable to households earning 81 to 120% of the area median income (AMI).
- Middle Income Units : Middle Income Units are units with rents that are affordable to households earning 121 to 165% of the area median income (AMI).
- Other Income Units : Other Units are units reserved for building superintendents.
- Studio Units : Studio Units are units with 0-bedrooms.
- 1-BR Units : 	1-BR Units are units with 1-bedroom
- 2-BR Units : 2-BR Units are units with 2-bedrooms.
- 3-BR Units : 3-BR Units are units with 3-bedrooms.
- 4-BR Units : 	4-BR Units are units with 4-bedrooms.
- 5-BR Units : 5-BR Units are units with 5-bedrooms.
- 6-BR+ Units : 6-BR+ Units are units with 6-bedrooms or more.
- Unknown-BR Units : Unknown-BR Units are units with an unknown number of bedrooms.
- Counted Rental Units : 	
Counted Rental Units are the units in the building, counted toward the Housing New York plan, where assistance has been provided to landlords in exchange for a requirement for affordable units.
- Counted Homeownership Units : Counted Homeownership Units are the units in the building, counted toward the Housing New York Plan, where assistance has been provided directly to homeowners.
- All Counted Units : The Counted Units field indicates the total number of affordable units, counted towards the Housing New York plan, that are in the building.
- Total Units : The Total Units field indicates the total number of units, affordable and market rate, in each building.

### Exploratory Data Analysis :

The report analysis depicts that :
- The dataframe has 5631 rows and each row represents a housing project.
- The dataframe has 41 features(columns).
- info() method hepls in knowing the quick description about the dataframe.

### Data Cleaning and Feature Engineering :


#### Observations :

- Census Tract and NTA has only 4502 entries, Latitude and Longitude has 4496 whereas Building Completion Date has only 4061 entries which means the remaining values are missing in these columns.
- Census Tract,NTA - Neighborhood Tabulation Area,Building Completion Date ,Reporting Construction Type,Extended Affordability Only ,Prevailing Wage Status attributes are of object Data type and the values in this attribute is repetitive which means that it is probably categorical attribute. 
- The value counts method can be used to find the categories(below).
- Latitute and logitude columns are of type float.
- All the income units and units attributes are of type int.
- Dropping the unncecesary columns :

   - 'Project Name','Project Start Date','Project Completion Date' as they have multiple NULL values.
   - 'Building ID','Number','Street','Postcode' as we extracted the main information from them.
   - 'BBL','BIN','Community Board','Latitude (Internal)','Longitude (Internal)','Council District' because they depict the existing information in the        dataset.

### EDA
#### Observations :

- Most the units are located in between -70.05 to -73.9 longitude and 40.65 to 40.90 latitiude.
- The Borough is the borough where the building is located.
- The above Geographical Distribution represents the count of building units at a particular location.
- The units are highly distributed between -74.0 to -73.9 Longitute and 40.6 to 40.87
- By observing the Histogram more closely, the values of Low Income Units are clustered around 0 and 50 but some Low Income Units goes beyond 50. I will     create an income category attribute with 5 categories which are labeled from 60 to 300.
- It is observed that 5 and 6BR+ units have negative correlation when compared with Moderate Income Units.
- It is because moderate units include less than 5-BR.
- It moslty include 2-4BR units.
- The report generated shows thr Extended Affordability Only field indicates whether the project is considered to be Extended Affordability.
- An extended affordability project involves no construction, but secures an extended or new regulatory agreement. 
- All extended affordability projects have a ‘reporting construction type’ of ‘preservation(yes /no). 
- The graph depicts that most of the houses are under non-prevailing wage.
- It is far beyong the requirements and it is not meeting the required criteria.
- From the observations most of the construction type is preservation.
- There is no large marginal difference between the two categories.
- Other Units are units reserved for building superintendents.
- The reserved units are around 900.
- 5-BR unit distribution that is being included is very less
- 6-BR+ unit distribution that is being included is far less than 5-BR

### Conclusion :

The bedroom units are clearly liked to the project income units. So estimating the total units that can be efficiently produced using these features will be my next step od the project.



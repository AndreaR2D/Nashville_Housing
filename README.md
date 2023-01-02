# Nashville_Housing

Analysis of the Nashville 2013-2016 house market


## Tools used
Excel, PowerBI, QGIS, Powerpoint


## Data Profiling

This dataset contains informations about the Nashvilles house market between 2013 and 2016. Each record have the location, the price, the sale date, specifications, owner name, ....


Before cleaning:

> 32 Columns;
> 56 640 records

After cleaning:

> 29 Columns;
> 56 465 records

Data Types:

> * INT: [Unique ID; Sale Price; Land Value; Building Value; Total Value; Year Built; Bedrooms; Full Bath; Half Bath]
> * String: [Parcel ID; Land Use; Property Adress; Street Name; Suite/Condo#; Property City; Legal Reference; Sold As Vacant; Multiple Parcel; Owner Name; Adress; Tax District; Neightborhood; Finished Area; Foundation Type; Exterior Wall; Grade; Owner Type]
> * Date: [Sale Date]
> * Float: [Acreage]


## Data cleaning


#### List of the data errors and how I've cleaned it with Excel

Delete useless columns and why

> - State: Every house/appt are in TN.
> - Unamed 1st colum: Duplicate with the "Unnamed: 0" column. Which I've renamed in "Unique ID".
> - City: Duplicate with the "Property city column", the Rows without Owner were blank.
> - Image: Useless since I can't have access to the image. 


Extract the street name of the property address

> I've created a new column and extract the adress name with the shortcut CTRL + E. 


Populate the NULL street name

> I've used the Parcel ID to find the street name. I've extracted the Parcel ID and Street Name column into a new tab. Then I delete the rows with NULL Street name. This new tab contain all the parcel ID with a valid street name. Last step on the main tab: Vlookup on the Street Name with its Parcel ID searching into the Parcel ID tab

Populate the NULL owner name

> Same method as the street name. Therefore there still are NULL values, I couldn't find the Owner name with its address.


Delete duplicates

> What define a duplicate ? If 2 rows have the same [Parcel ID; Property Adress; Sale Date; Sale Price; Legal Reference]. I assume they are duplicates. I've used the remove duplicate tool with the specified column select. 167 Duplicates found and deleted


Add an Owner Type column

> Corporation are defined by : LLC; TRUST; GP; INC; TRUSTEE; TRUSTS; TRUST; IRA; INCORPORATED; DREAMINC; LANDTRUST; PLLC. If they have one of this attribute in their name, I assume they are Corpo.

Add a Land Category column

> Categorize Land by category: Home; Commercial; Public; Religious; 


Normalize names

> Some Land Use names were written differently but had the same meaning.

## Data Visualization

Viz made with PowerBI 

## Report

PowerPoint document 

* Infos about the city
* Market analysis
* Property Specs
* Owners
* Neightborhoods: I've used city public dataset from data.nashville.gov, extracted the centroid with QGIS then import the coordinates in PowerBI to link the orignal dataset 

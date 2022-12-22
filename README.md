# Nashville_Housing

Analysis of the Nashville 2013-2016 house market

## Data Profiling

This dataset contains informations about the Nashvilles house market between 2013 and 2016. Each record have the location, the price, the sale date, specifications, owner name, ....


Before cleaning:
32 Columns;
56 640 records

After cleaning:
28 Columns;
56 465 records


## Data cleaning


#### List of the data errors and how I've cleaned it with Excel

> Delete useless columns and why

- State: Every house/appt are in TN.
- Unamed 1st colum: Duplicate with the "Unnamed: 0" column. Which I've renamed in "Unique ID".
- City: Duplicate with the "Property city column", the Rows without Owner were blank.
- Image: Useless since I can't have access to the image. 


> Extract the street name of the property address

I've created a new column and extract the adress name with the shortcut CTRL + E. 


> Populate the NULL street name

I've used the Parcel ID to find the street name. I've extracted the Parcel ID and Street Name column into a new tab. Then I delete the rows with NULL Street name. This new tab contain all the parcel ID with a valid street name. Last step on the main tab: Vlookup on the Street Name with its Parcel ID searching into the Parcel ID tab


> Delete duplicates

What define a duplicate ? If 2 rows have the same [Parcel ID; Property Adress; Sale Date; Sale Price; Legal Reference]. I assume they are duplicates. I've used the remove duplicate tool with the specified column select. 167 Duplicates found and deleted

> 31 281 Properties without an owner have NULL values for the Property specifications

No clue for this error.

## Data Visualization

Viz made with PowerBI

* Infos about the city
* Sales Analysis
* Neightborhood
* Property Specs
* Owners





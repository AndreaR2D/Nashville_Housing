# Nashville_Housing

Analysis of the Nashville 2013-2016 house market

## Data Profiling


## Data cleaning


List of the data errors and how I've cleaned it with Excel:

- Extract the street name of the property adress:  I've created a new column and extract the adress name with the shortcut CTRL + E

- Populate the NULL street name: I've used the Parcel ID to find the street name. I've extracted the Parcel ID and Street Name column into a new tab. Then I delete the rows with NULL Street name. This new tab contain all the parcel ID with a valid street name. Last step on the main tab: Vlookup on the Street Name with its Parcel ID searching into the Parcel ID tab

- Delete duplicates: What define a duplicate ? If 2 rows have the same [Parcel ID; Property Adress; Sale Date; Sale Price; Legal Reference]. I assume they are duplicates.

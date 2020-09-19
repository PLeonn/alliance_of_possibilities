# alliance_of_possibilities

This project with two sets of data; one csv of food trucks in Chicago, IL, and the other a csv of census data from Illinois.  The census file was too large to import, so was reduced the information down to just Chicago information, and eliminated extraneous columns.  Once imported into Jupyter Notebook, it was determined which data to retain, then removed the rest.   Columns were re-named for clarification and consistency.  

The zip code column in the census dataframe had to be converted to int64 to remove the trailing .0, and was then grouped by zip code, and the index reset.  Both dataframes were merged on the zip code column as a left join to retain all food truck information and dropped any census data that applied to zip codes not in our food truck data.  
At this point, a connection was made to the Mongo DB Compass Community to establish the ChicagoFT database, and a by_business collection was established.  This collection includes separate documents for each food truck business and the business and census information associated with it.  

Next, a by_zip collection was created that has a document for each zip code, showing census data for that zip code, then an array with each food truck and its basic business information within that zip code.

[Image](https://github.com/https://github.com/PLeonn/alliance_of_possibilities/Resources/Food-Truck.jpg)

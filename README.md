# alliance_of_possibilities

<p align="center">
  <img width="460" height="300" src="Resources/Food-Truck.jpg">
</p>


This project includes two sets of data; one csv of food trucks in Chicago, IL, and the other a csv of census data from Illinois.  The census file was too large to import, so was reduced down to just Chicago information, and eliminated extraneous columns.  Once imported into Jupyter Notebook, it was determined which data to retain, and the rest was removed.   Columns were re-named for clarification and consistency.  

The zip code column in the census dataframe had to be converted to int64 to remove the trailing .0, and was then grouped by zip code, and the index reset.  Both dataframes were merged on the zip code column as a left join to retain all food truck information and drop any census data that applied to zip codes outside of the food truck data.  

At this point, a connection was made to the Mongo DB Compass Community to establish the ChicagoFT database, with by_business and by_zip collections established.  The by_business collection includes separate documents for each food truck business, with the business and census information associated with it.  The by_zip collection includes each zip code, showing census data for that zip code, then an array with each food truck and its basic business information within that zip code.

Sample queries were created to show possible searched within each collection.





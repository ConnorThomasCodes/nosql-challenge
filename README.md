# nosql-challenge

In this repository, we use our establishments.json file to create a noSQL database in MongoDB. This database is named 'uk_food' and has one collection 'establishments'.

After creating our database, we access it in PyMongo to verify it was properly created and populated, and then make some modifications before further analysis. First, we add an additional establishment 'Penang Flavours' according to some given data, and we parse our saved data to find a matching BusinessTypeID (ID = 1). Additionally, we also drop any establishments located in Dover and convert latitude and longitude to integers.

In our database analysis, we perform various queries, count the number ouf documents in our result, and then output the results to a dataframe each time. First, we filter for any establishments with a Hygiene Score equal to 20.

Next, we find establishments in London with a RatingValue greater than or equal to 4 (looking at all entries for rating value, we get many word strings and null values along with number strings for the integers '1'-'5', so we simply check if RatingValue is in ['4','5']).

After that, we filter for any establishments within 0.1 degrees of the latitude and longitiude of our new restaurant 'Penang Flavours' and also having RatingValue '5', sorted by lowest Hygiene Score, and limited to the lowest 5 entries.

Finally, we create an aggregation pipeline to group the establishments by 'LocalAuthorityName' and then count all entries with a Hygiene Score of 0. After our grouping is completed, we sort in descending order to see the localities with the largest number of establishments with Hygiene Score 0.

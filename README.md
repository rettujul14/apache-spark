The is a spark job that I did as a project. The project details are as follows:

1. Cleanup (Spark Job): A sample dataset of request logs is given in DataSample.csv. Here we  consider records that have identical geoinfo and timest as suspicious. Inorder to clean up the dataset, i have created another dataframe which contains only the ID's which have same geoinfo and timest, then performed a left join between the new data frame and the original data frame.

2. Label (Spark Job): A list of POI (point of interest) locations is presented in POIList.csv. Please assign each request in the DataSample.csv to one of those POI locations that has minimum distance to the request location. Inoder to perform this operation, first i have defined a funtion to calculate the distance between two point based on latitude and longitude. Then cross joined the POIList.csv dataset to the sample dataset. Then calculated the distance between two points and created a new column to save the result. Then assigned each request to the closest POI.

3. Analysis (Spark Job): a) With respect to each POI location, calculated the average and standard deviation of distance between the POI location to each of its assigned records. b) Calculated the radius and density (requests/area) for each POI

4. Model: To visualize the popularity of the POI locations, mapped the density of POIs into a scale from -10 to 10. Created a mathematical model to implement the mapping. 

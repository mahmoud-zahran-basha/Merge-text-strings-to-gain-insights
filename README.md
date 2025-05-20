## Merge text strings to gain insights
  # the data from bigquery-public-data.new_york.citibike_trips
  # Merge text strings to gain insights
  # use my sql PhpMyAdmin

## we will use 

 # concat
 # COUNT 
 # ROUND
 # CAST 
 # AVG 
 
### code used
  SELECT
 usertype,
 concat (start_station_name ," to " , end_station_name) AS route, 
 COUNT(*) as num_trips,
 ROUND(AVG(CAST(tripduration AS UNSIGNED)/60),2) AS duration
 FROM
  citibike_trips
  GROUP BY
  start_station_name,end_station_name,usertype
  ORDER BY
  num_trips DESC
  LIMIT
  12

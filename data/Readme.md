#### Big Data Inspection - NYC Taxi Trips 
1. What datetime range does your data cover?  How many rows are there total?<br>
-> 1. The datetime range the dataset covers is from 2013-02-01 00:00:00 to 2013-02-28 23:59:59.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. The total no.of rows the dataset carries is 13990177.

2. What are the field names?  Give descriptions for each field.<br>
-> Here is the description of the fields in the dataset:<br>
<b>Medallion</b> : Medallion number means the identification number issued by the license commission. Which represents that the vehicle is allowed to be driven.<br>
<b>Hack_license</b> : Hack license is a license to drive a taxi or other passenger car for hire.<br>
<b>Vendor_id</b> : It is a unique id indicating the provider associated with the trip record.<br>
<b>Rate_code</b> : It is how the taxi fares are calculated. For example, if the rate code is 1 it means it is charged as in the limit within the city. If the rate code is 5 it means the charge is calculated as out of the city.<br>
<b>Store_and_fwd_flag</b> : This flag indicates whether the trip record was held in vehicle memory before sending to the vendor because the vehicle did not have a connection to the server. For example, Y means store and forward, N means not store and forward the trip.<br>
<b>Pickup_datetime</b> : Date and time when the meter starts.<br>
<b>Dropoff_datetime</b> : Date and time when the meter stops.<br>
<b>Passenger_count</b> : No.of passengers travelled in the vehicle.<br>
<b>Trip_time_in_secs</b> : It represents how much time the trip has been taken place in seconds.<br>
<b>Trip_distance</b> : The distance covered in that particular trip.<br>
<b>Pickup_longitude</b> : Longitude where the meter was engaged.<br>
<b>Pickup_latitude</b> : Latitude where the meter was engaged.<br>
<b>Dropoff_longitude</b> : Longitude where the meter was disengaged.<br>
<b>Dropoff_latitude</b> : Latitude where the meter was disengaged.<br>


3. Give some sample data for each field.<br>
-> Here is the few rows of the data from the dataset:

medallion | hack_license | vendor_id | rate_code | store_and_fwd_flag | pickup_datetime | dropoff_datetime | passenger_count | trip_time_in_secs | trip_distance | pickup_longitude | pickup_latitude | dropoff_longitude | dropoff_latitude
--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---| --- | --- 
1B5C0970F2AE8CFFBA8AE4584BEAED29 | D961332334524990D1BBD462E2EFB8A4 | CMT | 1 | N | 2013-02-08 23:35:14 | 2013-02-08 23:42:58 | 1 | 463 | .80 | -73.992439 | 40.724487 | -73.984421 | 40.718903
B42249AE16E2B8E556F1CB1F940D6FB4 | D4BB308D1F3FCB3434D9DB282CDC93D7 | CMT | 1 | N | 2013-02-07 12:20:16 | 2013-02-07 12:50:27 | 4 | 1810 | 3.10 | -73.989494 | 40.769588 | -73.990303 | 40.737347
890699222C47C09FBC898758CEC69762 | 6318C3AEC02248928C3345B5805EB905 | CMT | 1 | N | 2013-02-08 08:56:54 | 2013-02-08 08:59:43 | 1 | 168 | 1.00 | -73.963036 | 40.799141 | -73.972168 | 40.786446
74B7D835C2CD98606D5256DA8A38E045 | D5E278C918256D1F97680A1F04D290E0 | CMT | 1 | N | 2013-02-08 09:37:02 | 2013-02-08 09:50:50 | 1 | 828 | 2.10 | -73.987953 | 40.728764 | -74.007118 | 40.705399
4003B8478418FEC5D761E2F37602769B | 0B766F1054A5C16D86BC023858BD8143 | CMT | 1 | N | 2013-02-08 19:31:25 | 2013-02-08 19:46:23 | 1 | 897 | 3.30 | -73.987282 | 40.743042 | -74.010284 | 40.703964
D72DF7B12201912BFDBB93081EF04C96 | AFD828EEF790A2485BBB0B568A8BE22E | CMT | 1 | N | 2013-02-08 23:10:01 | 2013-02-08 23:46:15 | 4 | 2173 | 7.60 | -73.993004 | 40.720154 | -73.959747 | 40.80854

4. What MySQL data types / len would you need to store each of the fields?<br>
&nbsp;&nbsp;&nbsp;&nbsp;a. int(xx), varchar(xx),date,datetime,bool, decimal(m,d)<br>
-> The datatypes of the fields in the dataset are:<br>
<b>Medallion :</b> varchar(35)<br>
<b>Hack_license :</b> varchar(35)<br>
<b>Vendor_id :</b> varchar(3)<br>
<b>Rate_code :</b> int(1)<br>
<b>Store_and_fwd_flag :</b> varchar(1)<br>
<b>Pickup_datetime :</b> datetime<br>
<b>Dropoff_datetime :</b> datetime<br>
<b>Passenger_count :</b> int(1)<br>
<b>Trip_time_in_secs :</b> int(5)<br>
<b>Trip_distance :</b> decimal(1,2)<br>
<b>Pickup_longitude :</b> decimal(2,6)<br>
<b>Pickup_latitude :</b> decimal(2,6)<br>
<b>Dropoff_longitude :</b> decimal(2,6)<br>
<b>Dropoff_latitude :</b> decimal(2,6)<br>

5. What is the geographic range of your data (min/max - X/Y)?<br>
&nbsp;&nbsp;&nbsp;&nbsp;a. Plot this (approximately on a map)<br>
-> Here are the minimum and maximum values for latitude and longitude:<br> 
Minimum value in the 'pickup_latitude' row: 40.5<br>
Maximum value in the 'pickup_latitude' row: 40.899998<br>
Minimum value in the 'pickup_longitude' row: -74.25<br>
Maximum value in the 'pickup_longitude' row: -73.700035<br>
Minimum value in the 'dropoff_latitude' row: 40.5<br>
Maximum value in the 'dropoff_latitude' row: 40.899994<br>
Minimum value in the 'dropoff_longitude' row: -74.25<br>
Maximum value in the 'dropoff_longitude' row: -73.700005<br>
Below is the map that has been plotted:<br>
![](Images/IMG-0003.jpg)

6. What is the average computed trip distance? (You should use Haversine Distance)<br>
&nbsp;&nbsp;&nbsp;&nbsp;a. Draw a histogram of the trip distances binned anyway you see fit.<br>
-> Average Haversine Distance: 19.48 km<br>
![](hist.png)

7. What are the distinct values for each field? (If applicable)<br>

Name | Value
--- | ---
medallion | 13415
hack license | 32062
vendor id | 2
rate code | 12
store and fwd flag | 3
pickup datetime | 2099113
dropoff datetime | 2101381
passenger count | 12
trip time in secs | 6159
trip distance | 4233
pickup longitude | 40276
pickup latitude | 40276
dropoff longitude | 56207
dropoff latitude | 88544

8. For other numeric types besides lat and lon, what are the min and max values?<br>
-> Here are the minimum and maximum for the values that are applicable:<br>
Minimum Value of rate_code: 0  Maximum Value of rate_code: 79<br>
Minimum Value of datetime: 2013-02-01 00:00:00  Maximum Value of datetime: 2013-02-28 23:59:59<br>
Minimum Value of passenger count: 0  Maximum Value of passenger count: 208<br>
Minimum Value of trip time in seconds: 0  Maximum Value of trip time in seconds: 10800<br>

9. Create a chart which shows the average number of passengers each hour of the day. (X axis should have 24 hours)<br>
-> Below is the chart for the given values:<br>
![](plotmain.png)

10. Create a new CSV file which has only one out of every thousand rows.<br>
-> Created the csv file with the reduced data i.e., for every thousand rows I have taken 1 entry and stored in the csv named reduced.csv<br>

11. Repeat step 9 with the reduced dataset and compare the two charts.<br>
-> Below is the chart for the reduced dataset:<br>
![](plot.png)

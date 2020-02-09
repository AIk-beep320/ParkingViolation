# ParkingViolation
Parking Violation Tickets Analysis

# For task1: 
Data is available on
https://www.propublica.org/datastore/dataset/chicago-parking-ticket-data.
The data on violation tickets issued between 2007-01-01 to 2009-12-31 of size 2.18GB can be downloaded in CSV format.
- Pyspark code is used for filtering and exploring the dataset ('01-task1/main/Load-Explore-PySpark.txt')
- R code is used for cleaning the filtered dataset (text errors) and graphing 
('01-task1/support_code/task1a-graph-R.txt', '01-task1/support_code/task1b-cleaning-R.txt')

# For task2: 
Data is downloaded from,
https://www.propublica.org/datastore/dataset/chicago-parking-ticket-data
which is 7.13GB CSV file and filtered latest month May, 2018 data for clustering analysis.
- PySpark code is used for loading, data pre-processing and filtering ('02-task2/main-steps/Clus-PreProcess-PySpark.txt')
- R code is used for retrieving latitude and longitude using Google API ('02-task2/support_code/Clus-GeocodingAPI-R.txt')
- Python3 is used for performing clustering analysis on the filtered dataset('02-task2/support_code/Clustering-Python.txt')


# The data has the following columns: 
ticket_number,  issue_date, violation_location, license_plate_number, license_plate_state, icense_plate_type, zipcode, violation_code, violation_description, unit, unit_description, vehicle_make, fine_level1_amount, fine_level2_amount, current_amount_due, total_payments, ticket_queue, ticket_queue_date, notice_level, hearing_disposition, notice_number , officer, address.

# Important Attributes/ Attributes used:
-	ticket_number: Unique ticket ID
-	issue_date: date and time of the ticket issued
-	violation_location: street address where the ticket was issued
-	violation_code: municipal code associated with the violation
-	violation_description: violation name
-	vehicle_make: automobile brand
-	fine_level1_amount: original ticket cost
-	total_payments: original ticket cost + late penalties 
-	ticket_queue: recent status of the ticket (‘Paid’, ‘Dismissed’, ‘Hearing Req’, ‘Notice’, ‘Court’, ‘Bankruptcy’, ‘Define’)


# Tools Used:
The data downloaded was large in size, so Apache spark was used as the tool of choice for handling the data. Specifically, python 3 and pyspark were selected from the spark family. The sql module of pyspark was used throughout the process. R and Python3 are also used as mentioned above.

# Outcomes:
This dataset has been used to look at the,
- total revenue generated from the parking tickets issued
- peak months, timings on a day
- common areas of violation
- clustering analysis to group the violation areas into low, medium and high which can be used for mapping if street addresses are converted to latitude and longitude

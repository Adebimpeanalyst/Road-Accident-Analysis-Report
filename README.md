## Road Accident Analysis SQL Report


### Introduction

This is a report of the analysis carried out on ROAD ACCIDENT DATA. The data covered a vast part of the United Kingdom, it is required to advise the government on how to improve road safety. This report will show careful observations of  a general cause of road accident, time with highest number of occurences, location with the most occurrence etc. 
 
### Data Sources

The data for this analysis was extracted from this database file accident_data_v1.0.0_2023.db


### Tools
- MySQL: For data extraction
- Excel: For Data cleaning 
- PowerBi: For data exploring and visulizaing


### Process

1. Data Extraction using SQL: Below is the query syntax for extracting the data
   
   ~~~SQL
   SELECT a.accident_index,a.accident_reference,a.accident_year,a.date,a.day_of_week,a.time,
   
   a.lsoa_of_accident_location,
   
   c.casualty_index,c.casualty_reference,c.sex_of_casualty,c.casualty_class,
   
   c.casualty_type,
    
   v.vehicle_index,v.vehicle_type,v.vehicle_reference,v.age_of_vehicle,v.age_of_driver,v.sex_of_driver,
   
   l.lsoa01cd,l.lsoa01nm,l.lsoa01nmw FROM accident AS a JOIN casualty AS c ON
   
   a.accident_index=c.accident_index JOIN vehicle AS v
   
   ON a.accident_index=v.accident_index JOIN lsoa AS l ON a.lsoa_of_accident_location=l.lsoa01cd
   
    LIMIT 1000;
   
![image](https://github.com/user-attachments/assets/bd441040-5451-4bc2-9012-c51a79935bda)

The dataset was extracted and saved in an Excel file
[accident_data.xlsx](https://github.com/user-attachments/files/16599153/accident_data.xlsx)

2. Data Cleaning with Excel: The extrcted dataset was loaded on the Excel software where it was cleaned by converting the data types and also filtering out irrelevant data.
3. Data visualization and exploration using PowerBI.



### Reports

![image](https://github.com/user-attachments/assets/23563f7f-c6a0-4a60-9c7c-1d275694f9cc)

- The analysis reveals significant patterns in the timing and frequency of accidents. Notably, Wednesday has the highest number of accidents, with an average of 210 incidents occurring on this day. In terms of the specific hour, the peak time for accidents is at 3:50
 PM, with an average of four recorded accidents at that time.
- The analysis also focused on specific types of motorcycles, including motorcycles 125cc and under, motorcycles 125cc to 500cc, and motorcycles 500cc and over. It was found that accidents involving these motorcycles most frequently occur at 1:50 PM, and the day of the week with the highest occurrence is Saturday.
- Pedestrian accidents also exhibit particular patterns. Saturdays see the highest involvement of pedestrians in accidents, with 9:00 AM being the peak hour for such incidents.
- Regarding location, Westminster 02, as per the LSOA register, recorded the highest number of accidents. This suggests a notable concentration of incidents in that area.
- Further analysis indicates that weekdays see the highest number of accidents on Wednesdays, while weekends have the most accidents on Saturdays. These findings suggest the need for a deeper investigation into the underlying causes of the increased accident rates during these specific times to develop effective preventative measures.


# MIST 4610 Project 2

## Team name and members:

Group 1
- Alvia Pham: 
- Essex Glowaki: 
- Josh Torres: 
- Kenneth Johnson: 
- McKenna Sloan: 
- Thai Le: https://github.com/thai-tran-le/MIST4610-Project-2.git


## Dataset Description
The dataset is sourced from incidents of crime in the City of Los Angeles dating back to 2020. The data is transcribed from original crime reports that are typed on paper.There are 847726 columns and 28 rows.

This dataset contains a range of information, each row represents a unique crime event. In this  dataset, the 'DR_NO' column is of integer data type, representing the report number for each crime incident. The 'Date Rptd,' 'DATE OCC' columns are of date/time data types, capturing the reporting date, date of occurrence, and 'TIME OCC' in integer to represent the number of occurrences of the crime. Geographic details are captured through 'AREA' (integer) and 'AREA NAME (string) representing the numeric code and name of the geographic area. Other columns include 'Crm Cd' (integer) and 'Crm Cd Desc' (string) providing a numeric code and description for the type of crime, and 'Vict Age,' (string) 'Vict Sex,' and 'Vict Descent,' both in integer describing the victim's age, gender, and descent. 

“Premis Cd” (integer) and “Premis Desc” (string) describe the numeric code and name of the crime location type (condo, police station, etc). Various codes and descriptions are provided for weapon use, and the status of the crime report, such as “Weapon Used Cd” (integer), “Status” (string), “Status Desc” (string); and “Crm Cd 1”, “Crm Cd 2”, “Crm Cd 3”, “Crm Cd 4” all in integers. Crime address is described specifically with “LOCATION” and “Cross Street” both in strings. Additionally, 'LAT' and 'LON' columns both in floats offer precise latitude and longitude coordinates for each crime incident. 

## Data Dictionary
<img width="381" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/c1e8fef7-4d94-4188-a808-ab894b726c3a">
<img width="380" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/6b0b4aad-3cc5-4bdc-aadb-cf24ac5ecef2">


## Question 1
Of the most prevalent types of crimes committed, where do a majority of them take place?

<img width="479" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/5db0ac6c-d880-4c1b-a78f-f81e51e3bfdf">

Importance: 

The specific locations of crimes committed is extremely important for police to determine where to allocate their resources. For example, if they assigned the same number of police officers to each area within LA, some communities would be disproportionately patrolled. This would leave under-patrolled areas with too many crimes for their officers to respond to, which would result in a slow response rate, an inefficient use of police funds, and an increase in preventable crimes. However, if we can pinpoint the main locations where common crimes take place, these issues could be significantly reduced.


Manipulations to dataset: 

There were two main manipulations made to our dataset. First, the “Crm Cd Desc” (the description of the type of crime) had to be categorized into broader classifications. For example, this column contained descriptions like “Theft from Motor Vehicle,” “Theft from Person”, “Theft, Coin Machine,” etc. These slight differences were irrelevant to our initial calculation, so we created groups (such as “Theft”) in order to aggregate them together. The second manipulation we made was a calculated field, called “% Crm Cd Desc (group)”. This calculation was needed for the pie chart visualizations in order to determine the percentage of specific cases reported, as a proportion of the total cases reported. We calculated this by counting the number of unique IDs for each type of crime and dividing that amount by the total number of unique IDs for the dataset. The inputs for the calculation were: “COUNT([Dr No]) / TOTAL(COUNT([Dr No]))” and the outputs allowed us to determine how common each type of crime truly is.


Analysis and Results: 

We created four total charts to narrow down and eventually pinpoint the main location of the most common types of crime. First, we created a pie chart to determine that the most common type of crime committed was theft, which accounted for 48.89% of all crimes committed. Of the “Theft” crime type, there were many different sub-categories that had to be sorted through. Using a bar chart, we determined that the most common type of theft was stolen vehicles. Then, we created a symbol map to show the location where each vehicle was stolen. We determined that “77th Street'' was the area most prone to vehicle thefts, with “Newton” being a close second. Next, we used a piechart to conclude that 86.82% of vehicles stolen around “77th Street'' and “Newton” were stolen from a street (as opposed to a parking deck, driveway, etc.). Finally, we sorted these results by street name, which showed us that the three streets most prevalent to car thefts were “Broadway,” “Central Ave,” and “Main Street.” 


These results showcase the specific streets that police should be focusing their efforts on. They should be allocating more of their resources to streets like “Broadway,” which has had 83 cars stolen since 2020, as opposed to “Woodlawn” or “West 84th” which have each only had 1 car theft in the same time span. This will allow police to respond to reports quicker, use their funds more efficiently, and keep these areas safer for their community members.


## Question 2:
How have the monthly counts of identity theft incidents between genders changed?

<img width="580" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/aa184506-c8a4-4237-8b33-48473035bef7">


Importance: 

This question implies a focus on the comparative analysis of identity theft incidents affecting different genders over time, looking to uncover patterns, trends, or anomalies specific to each gender throughout a given period. In the advent of the pandemic, an acceleration of digital transition occurred. More services and financial activities were moved online, making scams and data breaches all the more abundant and sophisticated. By narrowing down the demographics for targets of these attacks, we can analyze trends to enable cybersecurity experts and policymakers at a governmental and corporate level to combat identity theft through reinforcing online safety protocols and potentially adjusting the legal framework for better victim assistance. Service providers and financial institutions can enhance their fraud detection systems to potentially reduce the incidences and impacts of these crimes. Overall, this question is a great start to highlighting the need for a tailored cybersecurity approach that addresses the unique challenges faced by different demographics.


Manipulations to dataset: 

One such manipulation we made to our data set was filtering out the month of November 2023 because it displayed a result that was outside the range of possibilities when taking the rest of the data set into account. We presumed that this outlier in the data set had to do with the fact that November was not yet finished at the time of our analysis. The second manipulation was to the Date Occ pill in the columns to show the month and the years with discrete values instead of continuous to present the data at their respective points in time more accurately.


Analysis and Results: 

The graph indicates a significant divergence in trends of identity theft cases between females and males from 2020 to 2023. The pink line, representing females shows a relatively stable trend in 2020, followed by a sharp increase in reported identity theft cases beginning in 2021. This surge peaks sharply, the drops just as rapidly, suggesting a temporary but intense vulnerability or a series of events that particularly affected females. In contrast, the blue line, representing males, maintains a relatively flat trend throughout the same period, indicating a steady rate of identity theft cases with not as dramatic peaks. The linear graph is the optimal choice for visualizing this data as it visually depicts a rate of change to add emphasis on the rapid growth of identity theft between the two groups. This is important for analysts and decision-makers to determine the magnitude and timing of the events and to uniform further investigation into potential causes and remedies for the disparities observed.



## Dataset Used
https://catalog.data.gov/dataset/crime-data-from-2020-to-present

<img width="473" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/3cb655b0-a0d1-4b60-a075-f4f8a866ab53">

# Group 5 Mist 4610 Project 2

# Team Name:

39217 Group 5

# Team Members:

1. Becca Paden @beccapaden
2. Charlotte Moore @cem62831
3. Gabe Hanes @gabehanes
4. Tyler Haleblian @tah52351
5. Logan Carras @lgc52432

# Dataset Description:
Dataset Link: https://catalog.data.gov/dataset/motor-vehicle-collisions-crashes

The dataset our group chose for this project is data from all motor vehicle collisions that happened in New York City. This data is sourced from data.gov.

This data covers all important aspects of the collision, including:
- The borough (district) that the crash happened in and the zip code of the area.
- The street name where the collision happened, as well as cross streets.
- What type of vehicle each involved in the collision was
- A contributing factor of each involved vehicle for why they collided
- The collison’s date and time

The dataset also includes additional measures:
- How many pedestrians, cyclists, motorists, and total persons were injured in the collision and how many died as a result of the collision.

The data set includes:
- 2.13 million rows
- 29 columns
- Text fields include borough, crash date, crash time, location, 5 vehicle codes, and 5 contributing factors
- Number fields include a collision id, number or persons injured, number of persons killed, number of pedestrians injured, number of pedestrians killed, number of cyclist injured, number of cyclist killed, number of motorist injured, number of motorist killed
- Each row is a motor vehicle collision 

# Questions

Question 1: Which contributing factors lead to the greatest number of injured pedestrians vs killed pedestrians?

- Our first question hopes to use the difference in number of pedestrians who got injured as a result of a vehicle collision compared to the number of pedestrians who were killed for each contributing factor. 
- While we could just look at the total number of deaths each contributing factor caused, this would be skewed by the frequency of each factor, so being able to see which ones lead to deaths more often than just injuries will let us more accurately understand our dataset.
- This relates to the dataset as it lists out the most important contributing factor for each collision and specifies differences between pedestrian injuries and fatalities.

Question 2: What time of day has the most traffic accidents outside of the normal rush hour traffic?

- This question once again brings up a frequency bias If there are more cars on the road, there are more opportunities for collisions to occur. 
- To compensate for this, and because there is no applicable data for how many cars are on the road at each given time in the data set, we will not taking into consideration the collisions that occur during normal rush hour traffic, which is around 8am in the morning and 4pm in the evening. 
- Additionally, by using the year of the collision, we can compare the accidents from 2014 and 2024 to see if there are any differences in the last 10 years that would affect peak collision times.
- This question relates to our dataset as we are able to use count functions to determine how many collisions happened, and we are able to plot it on a line graph as the dataset relays what time each collision occurred.


# Manipulations
Question 1:
- To create the graph, we created a customer measure titled “Pedestrians Killed per Pedestrians Injured”, which displays the number of pedestrians killed divided by pedestrians injured.
- We put a filter to only show contributing factors that have happened more than twenty times, as otherwise the highest death to injured ratio would be “Animal Involvement”, with five injuries caused and one death caused.
- Beneath the comparison graph, we put an additional graph that showcases the number of pedestrians injured, with the exact number showcased for easy understanding of how frequently pedestrians were injured.
- On the comparison graph, the number above each bar showcases the number of deaths caused to further make it easier to see how rare deaths were in some cases.

Question 2:
- The crash time was grouped by the hour
- The crash time was changed to hour to be able to see the peaks and valleys by time of day to identify high-risk times
- The years were filtered to only show 2014 and 2024
- The collison ID was also changed to a count dimension to get the number of crashes for each hour



# Analysis and Results
Question 1:

- Creating a measure that divides the number of pedestrians killed by the number of pedestrians injured allows users visualize the most fatal types of contributing factors. This will help with traffic law regulation and administration, as policies can be more focused on the most fatal collision types.
- The factors that show the highest ratio are Illness, Tinted Windows, and Alcohol involvement. 
- Alcohol involvement happens the most frequently out of the three top factors, but Illness creates many more deaths compared to injuries.
- The data shows that a large volume of injuries does not directly translate to fatalities. Driver inattention and failure to yield for example cause a lot of injuries, but don’t have a high death to injury ratio.

<img width="630" alt="Screenshot 2024-11-20 at 12 53 29 PM" src="https://github.com/user-attachments/assets/d30764fa-b561-4467-bdf5-f41a9e6f6791">


Question 2:
- The Tableau visualization confirms the common assumptions that rush hours 8 AM as well as (4-6PM) have the highest number of crashes
- Ignoring peak traffic times, 2 p.m. sees a relative maximum in both 2014 and 2024, with 2014 having 10,000 more collisions than in 2024. A possible explanation for this apex in accidents could be volume on the road or distractions
- The number of crashes is significantly higher in 2014 and is more volatile too. In 2014, collisions trended upwards at a high rate through the day but is beginning to level out as we move to 2024.
- The number of crashes has been slowly decreasing since 2014. Even so, there has been very little change in the number of collisions that occur at night, which can be attributed to lack of necessary lighting infrastructure or police presence

<img width="567" alt="Screenshot 2024-11-20 at 3 22 13 PM" src="https://github.com/user-attachments/assets/a547b8db-f2dc-49a8-8c30-e5f3b1928d03">

# Tableau Packaged Workbook

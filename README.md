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

[Uploading PedestrainsKilled.twb…](<?xml version='1.0' encoding='utf-8' ?>

<!-- build 20243.24.1010.1014                               -->
<workbook original-version='18.1' source-build='2024.3.0 (20243.24.1010.1014)' source-platform='win' version='18.1' xmlns:user='http://www.tableausoftware.com/xml/user'>
  <document-format-change-manifest>
    <AnimationOnByDefault />
    <IntuitiveSorting />
    <IntuitiveSorting_SP2 />
    <MarkAnimation />
    <ObjectModelEncapsulateLegacy />
    <ObjectModelTableType />
    <SchemaViewerObjectModel />
    <SheetIdentifierTracking />
    <WindowsPersistSimpleIdentifiers />
  </document-format-change-manifest>
  <preferences>
    <preference name='ui.encoding.shelf.height' value='24' />
    <preference name='ui.shelf.height' value='26' />
  </preferences>
  <datasources>
    <datasource caption='Motor_Vehicle_Collisions_-_Crashes' inline='true' name='federated.1mhkisi1621l7t1atqc7z13bhdbx' version='18.1'>
      <connection class='federated'>
        <named-connections>
          <named-connection caption='Motor_Vehicle_Collisions_-_Crashes' name='textscan.1h4p36r007408x12tgpnb0tpkhx1'>
            <connection class='textscan' directory='C:/Users/logan/Downloads' filename='Motor_Vehicle_Collisions_-_Crashes.csv' password='' server='' />
          </named-connection>
        </named-connections>
        <relation connection='textscan.1h4p36r007408x12tgpnb0tpkhx1' name='Motor_Vehicle_Collisions_-_Crashes.csv' table='[Motor_Vehicle_Collisions_-_Crashes#csv]' type='table'>
          <columns character-set='UTF-8' header='yes' locale='en_US' separator=','>
            <column datatype='date' name='CRASH DATE' ordinal='0' />
            <column datatype='datetime' name='CRASH TIME' ordinal='1' />
            <column datatype='string' name='BOROUGH' ordinal='2' />
            <column datatype='integer' name='ZIP CODE' ordinal='3' />
            <column datatype='real' name='LATITUDE' ordinal='4' />
            <column datatype='real' name='LONGITUDE' ordinal='5' />
            <column datatype='string' name='LOCATION' ordinal='6' />
            <column datatype='string' name='ON STREET NAME' ordinal='7' />
            <column datatype='string' name='CROSS STREET NAME' ordinal='8' />
            <column datatype='string' name='OFF STREET NAME' ordinal='9' />
            <column datatype='integer' name='NUMBER OF PERSONS INJURED' ordinal='10' />
            <column datatype='integer' name='NUMBER OF PERSONS KILLED' ordinal='11' />
            <column datatype='integer' name='NUMBER OF PEDESTRIANS INJURED' ordinal='12' />
            <column datatype='integer' name='NUMBER OF PEDESTRIANS KILLED' ordinal='13' />
            <column datatype='integer' name='NUMBER OF CYCLIST INJURED' ordinal='14' />
            <column datatype='integer' name='NUMBER OF CYCLIST KILLED' ordinal='15' />
            <column datatype='integer' name='NUMBER OF MOTORIST INJURED' ordinal='16' />
            <column datatype='integer' name='NUMBER OF MOTORIST KILLED' ordinal='17' />
            <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 1' ordinal='18' />
            <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 2' ordinal='19' />
            <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 3' ordinal='20' />
            <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 4' ordinal='21' />
            <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 5' ordinal='22' />
            <column datatype='integer' name='COLLISION_ID' ordinal='23' />
            <column datatype='string' name='VEHICLE TYPE CODE 1' ordinal='24' />
            <column datatype='string' name='VEHICLE TYPE CODE 2' ordinal='25' />
            <column datatype='string' name='VEHICLE TYPE CODE 3' ordinal='26' />
            <column datatype='string' name='VEHICLE TYPE CODE 4' ordinal='27' />
            <column datatype='string' name='VEHICLE TYPE CODE 5' ordinal='28' />
          </columns>
        </relation>
        <metadata-records>
          <metadata-record class='capability'>
            <remote-name />
            <remote-type>0</remote-type>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias />
            <aggregation>Count</aggregation>
            <contains-null>true</contains-null>
            <attributes>
              <attribute datatype='string' name='character-set'>&quot;UTF-8&quot;</attribute>
              <attribute datatype='string' name='collation'>&quot;en_US&quot;</attribute>
              <attribute datatype='string' name='field-delimiter'>&quot;,&quot;</attribute>
              <attribute datatype='string' name='header-row'>&quot;true&quot;</attribute>
              <attribute datatype='string' name='locale'>&quot;en_US&quot;</attribute>
              <attribute datatype='string' name='single-char'>&quot;&quot;</attribute>
            </attributes>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CRASH DATE</remote-name>
            <remote-type>133</remote-type>
            <local-name>[CRASH DATE]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CRASH DATE</remote-alias>
            <ordinal>0</ordinal>
            <local-type>date</local-type>
            <aggregation>Year</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CRASH TIME</remote-name>
            <remote-type>134</remote-type>
            <local-name>[CRASH TIME]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CRASH TIME</remote-alias>
            <ordinal>1</ordinal>
            <local-type>datetime</local-type>
            <aggregation>Hour</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>BOROUGH</remote-name>
            <remote-type>129</remote-type>
            <local-name>[BOROUGH]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>BOROUGH</remote-alias>
            <ordinal>2</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>ZIP CODE</remote-name>
            <remote-type>20</remote-type>
            <local-name>[ZIP CODE]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>ZIP CODE</remote-alias>
            <ordinal>3</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>LATITUDE</remote-name>
            <remote-type>5</remote-type>
            <local-name>[LATITUDE]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>LATITUDE</remote-alias>
            <ordinal>4</ordinal>
            <local-type>real</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>LONGITUDE</remote-name>
            <remote-type>5</remote-type>
            <local-name>[LONGITUDE]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>LONGITUDE</remote-alias>
            <ordinal>5</ordinal>
            <local-type>real</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>LOCATION</remote-name>
            <remote-type>129</remote-type>
            <local-name>[LOCATION]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>LOCATION</remote-alias>
            <ordinal>6</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>ON STREET NAME</remote-name>
            <remote-type>129</remote-type>
            <local-name>[ON STREET NAME]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>ON STREET NAME</remote-alias>
            <ordinal>7</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CROSS STREET NAME</remote-name>
            <remote-type>129</remote-type>
            <local-name>[CROSS STREET NAME]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CROSS STREET NAME</remote-alias>
            <ordinal>8</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>OFF STREET NAME</remote-name>
            <remote-type>129</remote-type>
            <local-name>[OFF STREET NAME]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>OFF STREET NAME</remote-alias>
            <ordinal>9</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF PERSONS INJURED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF PERSONS INJURED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF PERSONS INJURED</remote-alias>
            <ordinal>10</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF PERSONS KILLED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF PERSONS KILLED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF PERSONS KILLED</remote-alias>
            <ordinal>11</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF PEDESTRIANS INJURED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF PEDESTRIANS INJURED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF PEDESTRIANS INJURED</remote-alias>
            <ordinal>12</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF PEDESTRIANS KILLED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF PEDESTRIANS KILLED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF PEDESTRIANS KILLED</remote-alias>
            <ordinal>13</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF CYCLIST INJURED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF CYCLIST INJURED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF CYCLIST INJURED</remote-alias>
            <ordinal>14</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF CYCLIST KILLED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF CYCLIST KILLED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF CYCLIST KILLED</remote-alias>
            <ordinal>15</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF MOTORIST INJURED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF MOTORIST INJURED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF MOTORIST INJURED</remote-alias>
            <ordinal>16</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>NUMBER OF MOTORIST KILLED</remote-name>
            <remote-type>20</remote-type>
            <local-name>[NUMBER OF MOTORIST KILLED]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>NUMBER OF MOTORIST KILLED</remote-alias>
            <ordinal>17</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CONTRIBUTING FACTOR VEHICLE 1</remote-name>
            <remote-type>129</remote-type>
            <local-name>[CONTRIBUTING FACTOR VEHICLE 1]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CONTRIBUTING FACTOR VEHICLE 1</remote-alias>
            <ordinal>18</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CONTRIBUTING FACTOR VEHICLE 2</remote-name>
            <remote-type>129</remote-type>
            <local-name>[CONTRIBUTING FACTOR VEHICLE 2]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CONTRIBUTING FACTOR VEHICLE 2</remote-alias>
            <ordinal>19</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CONTRIBUTING FACTOR VEHICLE 3</remote-name>
            <remote-type>129</remote-type>
            <local-name>[CONTRIBUTING FACTOR VEHICLE 3]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CONTRIBUTING FACTOR VEHICLE 3</remote-alias>
            <ordinal>20</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CONTRIBUTING FACTOR VEHICLE 4</remote-name>
            <remote-type>129</remote-type>
            <local-name>[CONTRIBUTING FACTOR VEHICLE 4]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CONTRIBUTING FACTOR VEHICLE 4</remote-alias>
            <ordinal>21</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>CONTRIBUTING FACTOR VEHICLE 5</remote-name>
            <remote-type>129</remote-type>
            <local-name>[CONTRIBUTING FACTOR VEHICLE 5]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>CONTRIBUTING FACTOR VEHICLE 5</remote-alias>
            <ordinal>22</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>COLLISION_ID</remote-name>
            <remote-type>20</remote-type>
            <local-name>[COLLISION_ID]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>COLLISION_ID</remote-alias>
            <ordinal>23</ordinal>
            <local-type>integer</local-type>
            <aggregation>Sum</aggregation>
            <contains-null>true</contains-null>
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>VEHICLE TYPE CODE 1</remote-name>
            <remote-type>129</remote-type>
            <local-name>[VEHICLE TYPE CODE 1]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>VEHICLE TYPE CODE 1</remote-alias>
            <ordinal>24</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>VEHICLE TYPE CODE 2</remote-name>
            <remote-type>129</remote-type>
            <local-name>[VEHICLE TYPE CODE 2]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>VEHICLE TYPE CODE 2</remote-alias>
            <ordinal>25</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>VEHICLE TYPE CODE 3</remote-name>
            <remote-type>129</remote-type>
            <local-name>[VEHICLE TYPE CODE 3]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>VEHICLE TYPE CODE 3</remote-alias>
            <ordinal>26</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>VEHICLE TYPE CODE 4</remote-name>
            <remote-type>129</remote-type>
            <local-name>[VEHICLE TYPE CODE 4]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>VEHICLE TYPE CODE 4</remote-alias>
            <ordinal>27</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
          <metadata-record class='column'>
            <remote-name>VEHICLE TYPE CODE 5</remote-name>
            <remote-type>129</remote-type>
            <local-name>[VEHICLE TYPE CODE 5]</local-name>
            <parent-name>[Motor_Vehicle_Collisions_-_Crashes.csv]</parent-name>
            <remote-alias>VEHICLE TYPE CODE 5</remote-alias>
            <ordinal>28</ordinal>
            <local-type>string</local-type>
            <aggregation>Count</aggregation>
            <scale>1</scale>
            <width>1073741823</width>
            <contains-null>true</contains-null>
            <collation flag='0' name='LEN_RUS' />
            <object-id>[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]</object-id>
          </metadata-record>
        </metadata-records>
      </connection>
      <aliases enabled='yes' />
      <column caption='Borough' datatype='string' name='[BOROUGH]' role='dimension' type='nominal' />
      <column caption='Collision Id' datatype='integer' name='[COLLISION_ID]' role='dimension' type='ordinal' />
      <column caption='Contributing Factor Vehicle 1' datatype='string' name='[CONTRIBUTING FACTOR VEHICLE 1]' role='dimension' type='nominal' />
      <column caption='Contributing Factor Vehicle 2' datatype='string' name='[CONTRIBUTING FACTOR VEHICLE 2]' role='dimension' type='nominal' />
      <column caption='Contributing Factor Vehicle 3' datatype='string' name='[CONTRIBUTING FACTOR VEHICLE 3]' role='dimension' type='nominal' />
      <column caption='Contributing Factor Vehicle 4' datatype='string' name='[CONTRIBUTING FACTOR VEHICLE 4]' role='dimension' type='nominal' />
      <column caption='Contributing Factor Vehicle 5' datatype='string' name='[CONTRIBUTING FACTOR VEHICLE 5]' role='dimension' type='nominal' />
      <column caption='Crash Date' datatype='date' name='[CRASH DATE]' role='dimension' type='ordinal' />
      <column caption='Crash Time' datatype='datetime' name='[CRASH TIME]' role='dimension' type='ordinal' />
      <column caption='Cross Street Name' datatype='string' name='[CROSS STREET NAME]' role='dimension' type='nominal' />
      <column caption='Pedestrains Killed per Pedestrians Injured' datatype='real' name='[Calculation_387872533576671232]' role='measure' type='quantitative'>
        <calculation class='tableau' formula='SUM([NUMBER OF PEDESTRIANS KILLED])/SUM([NUMBER OF PEDESTRIANS INJURED])' />
      </column>
      <column aggregation='Avg' caption='Latitude' datatype='real' name='[LATITUDE]' role='measure' semantic-role='[Geographical].[Latitude]' type='quantitative' />
      <column caption='Location' datatype='string' name='[LOCATION]' role='dimension' type='nominal' />
      <column aggregation='Avg' caption='Longitude' datatype='real' name='[LONGITUDE]' role='measure' semantic-role='[Geographical].[Longitude]' type='quantitative' />
      <column caption='Number Of Cyclist Injured' datatype='integer' name='[NUMBER OF CYCLIST INJURED]' role='measure' type='quantitative' />
      <column caption='Number Of Cyclist Killed' datatype='integer' name='[NUMBER OF CYCLIST KILLED]' role='measure' type='quantitative' />
      <column caption='Number Of Motorist Injured' datatype='integer' name='[NUMBER OF MOTORIST INJURED]' role='measure' type='quantitative' />
      <column caption='Number Of Motorist Killed' datatype='integer' name='[NUMBER OF MOTORIST KILLED]' role='measure' type='quantitative' />
      <column caption='Number Of Pedestrians Injured' datatype='integer' name='[NUMBER OF PEDESTRIANS INJURED]' role='measure' type='quantitative' />
      <column caption='Number Of Pedestrians Killed' datatype='integer' name='[NUMBER OF PEDESTRIANS KILLED]' role='measure' type='quantitative' />
      <column caption='Number Of Persons Injured' datatype='integer' name='[NUMBER OF PERSONS INJURED]' role='measure' type='quantitative' />
      <column caption='Number Of Persons Killed' datatype='integer' name='[NUMBER OF PERSONS KILLED]' role='measure' type='quantitative' />
      <column caption='Off Street Name' datatype='string' name='[OFF STREET NAME]' role='dimension' type='nominal' />
      <column caption='On Street Name' datatype='string' name='[ON STREET NAME]' role='dimension' type='nominal' />
      <column caption='Vehicle Type Code 1' datatype='string' name='[VEHICLE TYPE CODE 1]' role='dimension' type='nominal' />
      <column caption='Vehicle Type Code 2' datatype='string' name='[VEHICLE TYPE CODE 2]' role='dimension' type='nominal' />
      <column caption='Vehicle Type Code 3' datatype='string' name='[VEHICLE TYPE CODE 3]' role='dimension' type='nominal' />
      <column caption='Vehicle Type Code 4' datatype='string' name='[VEHICLE TYPE CODE 4]' role='dimension' type='nominal' />
      <column caption='Vehicle Type Code 5' datatype='string' name='[VEHICLE TYPE CODE 5]' role='dimension' type='nominal' />
      <column aggregation='Sum' caption='Zip Code' datatype='integer' default-format='*00000' name='[ZIP CODE]' role='dimension' semantic-role='[ZipCode].[Name]' type='ordinal' />
      <column caption='Motor_Vehicle_Collisions_-_Crashes.csv' datatype='table' name='[__tableau_internal_object_id__].[Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B]' role='measure' type='quantitative' />
      <column-instance column='[NUMBER OF PEDESTRIANS INJURED]' derivation='Sum' name='[sum:NUMBER OF PEDESTRIANS INJURED:qk]' pivot='key' type='quantitative' />
      <column-instance column='[NUMBER OF PEDESTRIANS KILLED]' derivation='Sum' name='[sum:NUMBER OF PEDESTRIANS KILLED:qk]' pivot='key' type='quantitative' />
      <column-instance column='[CRASH DATE]' derivation='Year' name='[yr:CRASH DATE:ok]' pivot='key' type='ordinal' />
      <layout dim-ordering='alphabetic' measure-ordering='alphabetic' show-structure='true' />
      <style>
        <style-rule element='mark'>
          <encoding attr='color' field='[:Measure Names]' type='palette'>
            <map to='#4e79a7'>
              <bucket>&quot;[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk]&quot;</bucket>
            </map>
            <map to='#e15759'>
              <bucket>&quot;[federated.1mhkisi1621l7t1atqc7z13bhdbx]&quot;</bucket>
            </map>
            <map to='#f28e2b'>
              <bucket>&quot;[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS KILLED:qk]&quot;</bucket>
            </map>
          </encoding>
          <encoding attr='color' field='[yr:CRASH DATE:ok]' type='palette'>
            <map to='#499894'>
              <bucket>2020</bucket>
            </map>
            <map to='#4e79a7'>
              <bucket>2012</bucket>
            </map>
            <map to='#59a14f'>
              <bucket>2016</bucket>
            </map>
            <map to='#79706e'>
              <bucket>2024</bucket>
            </map>
            <map to='#86bcb6'>
              <bucket>2021</bucket>
            </map>
            <map to='#8cd17d'>
              <bucket>2017</bucket>
            </map>
            <map to='#a0cbe8'>
              <bucket>2013</bucket>
            </map>
            <map to='#b6992d'>
              <bucket>2018</bucket>
            </map>
            <map to='#e15759'>
              <bucket>2022</bucket>
            </map>
            <map to='#f1ce63'>
              <bucket>2019</bucket>
            </map>
            <map to='#f28e2b'>
              <bucket>2014</bucket>
            </map>
            <map to='#ff9d9a'>
              <bucket>2023</bucket>
            </map>
            <map to='#ffbe7d'>
              <bucket>2015</bucket>
            </map>
          </encoding>
        </style-rule>
      </style>
      <semantic-values>
        <semantic-value key='[Country].[Name]' value='&quot;United States&quot;' />
      </semantic-values>
      <object-graph>
        <objects>
          <object caption='Motor_Vehicle_Collisions_-_Crashes.csv' id='Motor_Vehicle_Collisions_-_Crashes.csv_2EC199FCF1AC4DB3B50299BF88FEBF2B'>
            <properties context=''>
              <relation connection='textscan.1h4p36r007408x12tgpnb0tpkhx1' name='Motor_Vehicle_Collisions_-_Crashes.csv' table='[Motor_Vehicle_Collisions_-_Crashes#csv]' type='table'>
                <columns character-set='UTF-8' header='yes' locale='en_US' separator=','>
                  <column datatype='date' name='CRASH DATE' ordinal='0' />
                  <column datatype='datetime' name='CRASH TIME' ordinal='1' />
                  <column datatype='string' name='BOROUGH' ordinal='2' />
                  <column datatype='integer' name='ZIP CODE' ordinal='3' />
                  <column datatype='real' name='LATITUDE' ordinal='4' />
                  <column datatype='real' name='LONGITUDE' ordinal='5' />
                  <column datatype='string' name='LOCATION' ordinal='6' />
                  <column datatype='string' name='ON STREET NAME' ordinal='7' />
                  <column datatype='string' name='CROSS STREET NAME' ordinal='8' />
                  <column datatype='string' name='OFF STREET NAME' ordinal='9' />
                  <column datatype='integer' name='NUMBER OF PERSONS INJURED' ordinal='10' />
                  <column datatype='integer' name='NUMBER OF PERSONS KILLED' ordinal='11' />
                  <column datatype='integer' name='NUMBER OF PEDESTRIANS INJURED' ordinal='12' />
                  <column datatype='integer' name='NUMBER OF PEDESTRIANS KILLED' ordinal='13' />
                  <column datatype='integer' name='NUMBER OF CYCLIST INJURED' ordinal='14' />
                  <column datatype='integer' name='NUMBER OF CYCLIST KILLED' ordinal='15' />
                  <column datatype='integer' name='NUMBER OF MOTORIST INJURED' ordinal='16' />
                  <column datatype='integer' name='NUMBER OF MOTORIST KILLED' ordinal='17' />
                  <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 1' ordinal='18' />
                  <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 2' ordinal='19' />
                  <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 3' ordinal='20' />
                  <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 4' ordinal='21' />
                  <column datatype='string' name='CONTRIBUTING FACTOR VEHICLE 5' ordinal='22' />
                  <column datatype='integer' name='COLLISION_ID' ordinal='23' />
                  <column datatype='string' name='VEHICLE TYPE CODE 1' ordinal='24' />
                  <column datatype='string' name='VEHICLE TYPE CODE 2' ordinal='25' />
                  <column datatype='string' name='VEHICLE TYPE CODE 3' ordinal='26' />
                  <column datatype='string' name='VEHICLE TYPE CODE 4' ordinal='27' />
                  <column datatype='string' name='VEHICLE TYPE CODE 5' ordinal='28' />
                </columns>
              </relation>
            </properties>
          </object>
        </objects>
      </object-graph>
    </datasource>
  </datasources>
  <actions>
    <action caption='Highlight 1 (generated)' name='[Action1_27AFAA89F87C4376944C9B32F59382C2]'>
      <activation auto-clear='true' type='on-select' />
      <source type='sheet' worksheet='Sheet 2' />
      <command command='tsc:brush'>
        <param name='field-captions' value='YEAR(Crash Date)' />
        <param name='target' value='Sheet 2' />
      </command>
    </action>
  </actions>
  <worksheets>
    <worksheet name='Sheet 1'>
      <table>
        <view>
          <datasources>
            <datasource caption='Motor_Vehicle_Collisions_-_Crashes' name='federated.1mhkisi1621l7t1atqc7z13bhdbx' />
          </datasources>
          <datasource-dependencies datasource='federated.1mhkisi1621l7t1atqc7z13bhdbx'>
            <column caption='Contributing Factor Vehicle 1' datatype='string' name='[CONTRIBUTING FACTOR VEHICLE 1]' role='dimension' type='nominal' />
            <column caption='Pedestrains Killed per Pedestrians Injured' datatype='real' name='[Calculation_387872533576671232]' role='measure' type='quantitative'>
              <calculation class='tableau' formula='SUM([NUMBER OF PEDESTRIANS KILLED])/SUM([NUMBER OF PEDESTRIANS INJURED])' />
            </column>
            <column caption='Number Of Pedestrians Injured' datatype='integer' name='[NUMBER OF PEDESTRIANS INJURED]' role='measure' type='quantitative' />
            <column caption='Number Of Pedestrians Killed' datatype='integer' name='[NUMBER OF PEDESTRIANS KILLED]' role='measure' type='quantitative' />
            <column-instance column='[CONTRIBUTING FACTOR VEHICLE 1]' derivation='None' name='[none:CONTRIBUTING FACTOR VEHICLE 1:nk]' pivot='key' type='nominal' />
            <column-instance column='[NUMBER OF PEDESTRIANS INJURED]' derivation='Sum' name='[sum:NUMBER OF PEDESTRIANS INJURED:qk]' pivot='key' type='quantitative' />
            <column-instance column='[NUMBER OF PEDESTRIANS KILLED]' derivation='Sum' name='[sum:NUMBER OF PEDESTRIANS KILLED:qk]' pivot='key' type='quantitative' />
            <column-instance column='[Calculation_387872533576671232]' derivation='User' name='[usr:Calculation_387872533576671232:qk]' pivot='key' type='quantitative' />
          </datasource-dependencies>
          <filter class='categorical' column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[:Measure Names]'>
            <groupfilter function='union' user:op='manual'>
              <groupfilter function='member' level='[:Measure Names]' member='&quot;[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk]&quot;' />
              <groupfilter function='member' level='[:Measure Names]' member='&quot;[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS KILLED:qk]&quot;' />
            </groupfilter>
          </filter>
          <filter class='categorical' column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]'>
            <groupfilter function='except' user:ui-domain='relevant' user:ui-enumeration='exclusive' user:ui-marker='enumerate'>
              <groupfilter function='level-members' level='[none:CONTRIBUTING FACTOR VEHICLE 1:nk]' />
              <groupfilter function='member' level='[none:CONTRIBUTING FACTOR VEHICLE 1:nk]' member='&quot;Unspecified&quot;' />
            </groupfilter>
          </filter>
          <filter class='quantitative' column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk]' included-values='in-range'>
            <min>20</min>
          </filter>
          <filter class='quantitative' column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[usr:Calculation_387872533576671232:qk]' included-values='in-range'>
            <min>0.0050000000000000001</min>
          </filter>
          <shelf-sorts>
            <shelf-sort-v2 dimension-to-sort='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]' direction='DESC' is-on-innermost-dimension='true' measure-to-sort-by='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[usr:Calculation_387872533576671232:qk]' shelf='columns' />
          </shelf-sorts>
          <slices>
            <column>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[:Measure Names]</column>
            <column>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]</column>
            <column>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[usr:Calculation_387872533576671232:qk]</column>
            <column>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk]</column>
          </slices>
          <aggregation value='true' />
        </view>
        <style>
          <style-rule element='axis'>
            <encoding attr='space' class='0' field='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk]' field-type='quantitative' max='26043' min='-2442' range-type='fixed' scope='rows' type='space' />
            <encoding attr='space' class='0' field='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[usr:Calculation_387872533576671232:qk]' field-type='quantitative' max='0.17676771083416523' min='-0.024975927755329811' range-type='fixed' scope='rows' type='space' />
            <format attr='height' field='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]' value='134' />
          </style-rule>
          <style-rule element='cell'>
            <format attr='width' field='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]' value='41' />
          </style-rule>
          <style-rule element='header'>
            <format attr='height-header' value='10' />
          </style-rule>
          <style-rule element='label'>
            <format attr='text-orientation' field='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]' value='-90' />
          </style-rule>
        </style>
        <panes>
          <pane id='3' selection-relaxation-option='selection-relaxation-allow'>
            <view>
              <breakdown value='auto' />
            </view>
            <mark class='Automatic' />
            <style>
              <style-rule element='mark'>
                <format attr='mark-color' value='#499894' />
                <format attr='mark-labels-show' value='true' />
                <format attr='mark-labels-cull' value='true' />
                <format attr='mark-transparency' value='255' />
              </style-rule>
              <style-rule element='pane'>
                <format attr='minwidth' value='1230' />
                <format attr='maxwidth' value='1230' />
                <format attr='minheight' value='316' />
                <format attr='maxheight' value='316' />
                <format attr='aspect' value='0' />
              </style-rule>
            </style>
          </pane>
          <pane id='4' selection-relaxation-option='selection-relaxation-allow' y-axis-name='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[usr:Calculation_387872533576671232:qk]'>
            <view>
              <breakdown value='auto' />
            </view>
            <mark class='Automatic' />
            <encodings>
              <text column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS KILLED:qk]' />
            </encodings>
            <style>
              <style-rule element='mark'>
                <format attr='mark-color' value='#499894' />
                <format attr='mark-labels-cull' value='true' />
                <format attr='mark-labels-show' value='true' />
                <format attr='mark-transparency' value='255' />
              </style-rule>
            </style>
          </pane>
          <pane id='5' selection-relaxation-option='selection-relaxation-allow' y-axis-name='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk]'>
            <view>
              <breakdown value='auto' />
            </view>
            <mark class='Automatic' />
            <encodings>
              <text column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk]' />
            </encodings>
            <style>
              <style-rule element='mark'>
                <format attr='mark-color' value='#499894' />
                <format attr='mark-labels-cull' value='true' />
                <format attr='mark-labels-show' value='true' />
                <format attr='mark-transparency' value='255' />
              </style-rule>
            </style>
          </pane>
        </panes>
        <rows>([federated.1mhkisi1621l7t1atqc7z13bhdbx].[usr:Calculation_387872533576671232:qk] + [federated.1mhkisi1621l7t1atqc7z13bhdbx].[sum:NUMBER OF PEDESTRIANS INJURED:qk])</rows>
        <cols>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]</cols>
      </table>
      <simple-id uuid='{F95A0717-55D6-40C0-A4E9-AE95A2DBBF14}' />
    </worksheet>
    <worksheet name='Sheet 2'>
      <table>
        <view>
          <datasources>
            <datasource caption='Motor_Vehicle_Collisions_-_Crashes' name='federated.1mhkisi1621l7t1atqc7z13bhdbx' />
          </datasources>
          <datasource-dependencies datasource='federated.1mhkisi1621l7t1atqc7z13bhdbx'>
            <column caption='Collision Id' datatype='integer' name='[COLLISION_ID]' role='dimension' type='ordinal' />
            <column caption='Crash Date' datatype='date' name='[CRASH DATE]' role='dimension' type='ordinal' />
            <column caption='Crash Time' datatype='datetime' name='[CRASH TIME]' role='dimension' type='ordinal' />
            <column-instance column='[COLLISION_ID]' derivation='CountD' name='[ctd:COLLISION_ID:qk]' pivot='key' type='quantitative' />
            <column-instance column='[CRASH TIME]' derivation='Hour' name='[hr:CRASH TIME:ok]' pivot='key' type='ordinal' />
            <column-instance column='[CRASH DATE]' derivation='Year' name='[yr:CRASH DATE:ok]' pivot='key' type='ordinal' />
          </datasource-dependencies>
          <filter class='categorical' column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[yr:CRASH DATE:ok]'>
            <groupfilter function='except' user:ui-domain='relevant' user:ui-enumeration='exclusive' user:ui-marker='enumerate'>
              <groupfilter function='level-members' level='[yr:CRASH DATE:ok]' />
              <groupfilter function='union'>
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2012' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2013' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2015' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2016' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2017' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2018' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2019' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2020' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2021' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2022' />
                <groupfilter function='member' level='[yr:CRASH DATE:ok]' member='2023' />
              </groupfilter>
            </groupfilter>
          </filter>
          <slices>
            <column>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[yr:CRASH DATE:ok]</column>
          </slices>
          <aggregation value='true' />
        </view>
        <style />
        <panes>
          <pane selection-relaxation-option='selection-relaxation-allow'>
            <view>
              <breakdown value='auto' />
            </view>
            <mark class='Automatic' />
            <encodings>
              <color column='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[yr:CRASH DATE:ok]' />
            </encodings>
          </pane>
        </panes>
        <rows>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[ctd:COLLISION_ID:qk]</rows>
        <cols>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[hr:CRASH TIME:ok]</cols>
      </table>
      <simple-id uuid='{9F89E1C3-9AC5-4C99-981B-17CA29881146}' />
    </worksheet>
  </worksheets>
  <windows saved-dpi-scale-factor='1.25' source-height='37'>
    <window class='worksheet' maximized='true' name='Sheet 1'>
      <cards>
        <edge name='left'>
          <strip size='160'>
            <card type='pages' />
            <card type='filters' />
            <card type='marks' />
          </strip>
        </edge>
        <edge name='top'>
          <strip size='2147483647'>
            <card type='columns' />
          </strip>
          <strip size='2147483647'>
            <card type='rows' />
          </strip>
          <strip size='2147483647'>
            <card type='title' />
          </strip>
        </edge>
        <edge name='right'>
          <strip size='160'>
            <card param='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[:Measure Names]' show-morefewerbutton='false' type='filter' />
          </strip>
        </edge>
      </cards>
      <viewpoint>
        <highlight>
          <color-one-way>
            <field>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[:Measure Names]</field>
            <field>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:COLLISION_ID:ok]</field>
            <field>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 1:nk]</field>
            <field>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:CONTRIBUTING FACTOR VEHICLE 2:nk]</field>
          </color-one-way>
        </highlight>
      </viewpoint>
      <simple-id uuid='{73D5E21C-0A03-4594-83F2-3C9F72DCA446}' />
    </window>
    <window class='worksheet' name='Sheet 2'>
      <cards>
        <edge name='left'>
          <strip size='160'>
            <card type='pages' />
            <card type='filters' />
            <card type='marks' />
          </strip>
        </edge>
        <edge name='top'>
          <strip size='2147483647'>
            <card type='columns' />
          </strip>
          <strip size='2147483647'>
            <card type='rows' />
          </strip>
          <strip size='2147483647'>
            <card type='title' />
          </strip>
        </edge>
        <edge name='right'>
          <strip size='276'>
            <card pane-specification-id='0' param='[federated.1mhkisi1621l7t1atqc7z13bhdbx].[yr:CRASH DATE:ok]' type='color' />
          </strip>
        </edge>
      </cards>
      <viewpoint>
        <highlight>
          <color-one-way>
            <field>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[hr:CRASH TIME:ok]</field>
            <field>[federated.1mhkisi1621l7t1atqc7z13bhdbx].[none:COLLISION_ID:ok]</field>
          </color-one-way>
        </highlight>
      </viewpoint>
      <simple-id uuid='{CF4C2F35-EFD0-40E9-9C77-D1E9FA00259C}' />
    </window>
  </windows>
  <thumbnails>
    <thumbnail height='192' name='Sheet 1' width='192'>
      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
    </thumbnail>
    <thumbnail height='192' name='Sheet 2' width='192'>
      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
    </thumbnail>
  </thumbnails>
</workbook>
)



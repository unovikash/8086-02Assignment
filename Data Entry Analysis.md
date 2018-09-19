# Data Entry Analysis

#### Issues

1. No Timestamp on the data

   - <u>Issue-</u> Even though there is a significant difference in the distributions of planktons based on **time of the day**, the same is not collected in the sample data.

   - <u>Fix-</u> Add a column to capture the time of the day.

2. Unit of temperature

   - <u>Issue-</u> The unit of temperature is not mentioned in the metadata. Different people use different scale to measure the data.
   - <u>Fix-</u> Add temperature information in the metadata

3. Metadata is not clearly written

   - <u>Issue-</u> Though it is good to have a metadata in one of the data report, the metadata itself is not very polished. Metadata for temperature has an additional column of information, and even though we can assume it to explain the process of data retrieval, a wring assumption can affect the data conclusion.
   - <u>Fix-</u> Properly write the metadata with well named columns

4. Chlorophyll measured in?

   - <u>Issue-</u> The unit of measurement for Chlorophyll is not provided in the metadata.
   - <u>Fix-</u> Include unit of measurement for the Chlorophyll in the metadata.

5. *pond2010.xlsx* uses 'z' to identify the column for depth of the measurement

   - <u>Issue-</u> This can be vague, especially without any metadata
   - <u>Fix-</u> Either a metadata can be added, or the column name can be simply 'Depth', which is also consistent with other data.

6. Density is measured in

   - <u>Issue-</u> The unit of measurement for Density is not mentioned in the metadata
   - <u>Fix-</u> Add unit of measurement for Density in metadata

7. Tab names should be consistent

   - <u>Issue-</u> One of the table has tab name by station, while the other has by species.
   - <u>Fix-</u> Use consistent tab names

8. Station specific information should also be capture in a sheet

   - <u>Issue-</u> While Station A has information on its depths, there is no such information available for Station B in the report
   - <u>Fix-</u> Add sheets to capture Station specific data

9. All reports should have metadata

   - <u>Issue-</u> Even though we have two similar reports which shared the same metadata, it should always be provided for all the reports.
   - <u>Fix-</u> Add metadata for every report

10. What does a negative value of count signify

    - <u>Issue-</u> One of the report has a negative count (#) / Liter, what does it signify, since count cannot be negative
    - <u>Fix-</u> If there is a negative value in a report, add some annotations to support the observation or to simply add a note that the data can be an error.

11. What is Max Secchi for Station B

    - <u>Issue-</u> The terminologies must be capture in the metadata.
    - <u>Fix-</u> Add the terminologies to the metadata

#### Suggested Model to Capture these data

##### Model 1: To store Plankton's data

| Column Name             | Description                            |
| ----------------------- | -------------------------------------- |
| Date                    | Date of data capture                   |
| Time                    | Time of the day, the data was captured |
| Station                 | Station Name                           |
| Depth (unit)            | Depth in the unit provided             |
| Cuni (#/L)              | Count of Cuni per Liter                |
| Cuni Colony Size (mm)   | Average Colony Size                    |
| Chippo (#/L)            | Count of Chippo per Liter              |
| Chippo Colony Size (mm) | Average Colony Size                    |
| Chl A (unit)            | Chlorine measurement                   |
| Temp (unit)             | Temperature with Unit                  |

##### Model 2: To Store Station Data

| Column Name          | Description                                         |
| -------------------- | --------------------------------------------------- |
| Station Name         | Name of the Station (consistent across the reports) |
| Maximum Depth (unit) | Maximum depth of the pond                           |
| Minimum Depth (unit) | Minimum depth of the pond                           |

##### Model 3: To store Metadata

| Column Name                  | Description                                                |
| ---------------------------- | ---------------------------------------------------------- |
| Column Name                  | Name of the column                                         |
| Unit of Measurement (if any) | Any measurement unit if used                               |
| Description                  | Description to provide the story behind the data captured. |


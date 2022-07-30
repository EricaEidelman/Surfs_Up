# Surf's Up With Advanced Data Storage and Retrieval

## Project Overview
The purpose of this project is to understand the climate on the Hawaiian island of Oahu, in order to prove to potential investors that a year-round surf and ice cream shop is a profitable venture. Using an Sqlite file and SQLAlchemy, the file was queried to obtain summary climate statistics.

## Resources
Data Source: hawaii.sqlite

Software: Python 3.7.6

## Results
After obtaining the summary statistics for temperature in June and December, the following results were found:
- The mean temperature in June is just under 75°F and the mean temperature in December is just over 71°F.
- The minimum temperature in June is 64°F and the minimum temperature in December is 56°F.
- The maximum temperature in June is 85°F and the maximum temperature in December is 83°F.

Complete summary statistics for June are below:

![This is an image](https://github.com/EricaEidelman/Surfs_Up/blob/main/June_Summary.png)

Complete summary statistics for December are below:

![This is an image](https://github.com/EricaEidelman/Surfs_Up/blob/main/December_Summary.png)

## Summary
Based on the temperatures alone, the results show that a combination surf and ice cream shop would be profitable year round in Oahu. The average temperatures are the low to mid 70s all year, which would seem to be ideal for surfing and indulging in ice cream. December does have a few chilly days, but there are also days with temperatures in the 80s, which would make up for any slow times. 

Because surfing weather is also affected by precipitation, a few more queries can be done to judge if Oahu's weather is suitable. The first of these would be to identify precipitation levels in June. These results can be obtained as follows:
```
session.query(Measurement.prcp).filter(func.strftime("%m", Measurement.date) == "06").all()
```
What the query does is obtain the precipitation amounts for all dates where the month is June (the 6th month). The query can be slightly adjusted to obtain a second query which would then show the precipitation amount for December. The code follows:
```
session.query(Measurement.prcp).filter(func.strftime("%m", Measurement.date) == "12").all()
```
With an understanding of what Oahu's climate is like with regard to both temperature and precipitation, the investors would be able to judge whether the year-round surf and ice cream shop is a good choice to support.

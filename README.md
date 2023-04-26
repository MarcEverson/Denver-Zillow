# Denver-Zillow

We were thinking about buying a house in Denver to see if the investment was worth it. 

I found Zillow housing market data across the U.S. from 1996-2016.

I imported that into MySQL.

I wanted to first see the 10 year average increase in homes in Denver. 

SELECT AVG(`2016-08`) - AVG(`2006-08`) as 10_year_avg_change, RegionName
FROM Zillow.allhomes
WHERE RegionName = 'Denver' 
Group by 2

$92,730.19


I then compared that to the average of all homes across the U.S. 

SELECT State, AVG(`2016-08`) - AVG(`2006-08`) as 10_year_avg_change
FROM Zillow.allhomes 
Group by State
Order by 2 DESC

I found out that Denver as compared to other states would be 2nd on the list compared to all other states and Regions just behind D.C.

I then wanted to compare hosing prices to the rest of Colorado. 
SELECT  Metro, AVG(`2016-08`) - AVG(`2006-08`) as 10_year_avg_change
FROM Zillow.allhomes 
WHERE State = "CO"
Group by 1 
Order by 2 DESC


I found out that buying a house in Denver was a very sound investment based on this data as it was the second highest gain in value after Boulder at $143,711.11. 


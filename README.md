| What is needed  | Query |
| ------------- | ------------- |
| Not Toyota & 2019> & 7m< ord. by AutoID | SELECT * FROM Auto WHERE NOT CarBrand='Toyota' AND YearOfRelease > '2019' AND Price < 7000000 ORDER BY AutoID; |
| Last 7 cars ord. by AutoID | SELECT * FROM (SELECT * FROM Auto ORDER BY AutoID DESC LIMIT 7) ORDER BY AutoID;  |
| The most expensive car | SELECT CarBrand, Model, YearOfRelease, Price FROM Auto WHERE Price=(SELECT MAX(Price) FROM Auto); |
| Cars more exp. than 7.5m & cheaper than 2.5m ord. alph. by car brand & model vice versa  | SELECT CarBrand, Model, YearOfRelease, Price FROM Auto WHERE Price > 2500000 AND Price < 7500000 ORDER BY CarBrand ASC, Model DESC; |
| Cars start with "H" | SELECT * FROM Auto WHERE CarBrand LIKE 'H%' ORDER BY AutoID; |
| Count avg. car price | SELECT AVG(Price) AS PriceAvg FROM Auto; |
| Count distinct brands | SELECT COUNT(DISTINCT CarBrand) FROM Auto; |
| Upd. price of 19th car | UPDATE Auto SET Price='2500500' WHERE AutoID = 19; |
| Cars more exp. than 2.5m & cheaper than 4m & not 1st, 5th, 10th, 18th in the table | SELECT * FROM Auto WHERE Price BETWEEN 2500000 AND 4000000 AND AutoID NOT IN (1,5,10,18); |
| Count distinct car brands ord. by AutoID | SELECT COUNT(AutoID), CarBrand FROM Auto GROUP BY CarBrand ORDER BY COUNT(AutoID) ASC; |

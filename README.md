# WorldDatabaseQueries

Using count, get the number of cities in the USA:

```
SELECT COUNT(*) AS "# of Cities in USA"
FROM city
WHERE CountryCode="USA";
```

Find out what the population and average life expectancy for people in Argentina (ARG) is:

```
SELECT Name, Population, LifeExpectancy
FROM country
WHERE Name="Argentina:;
```

Display all the cities for any country of your choice besides the USA:

```
SELECT *
FROM city
WHERE countryCode="CAN";
```
Custom # 1:

```
SELECT city.Name, city.Population, count(country.Name)
FROM city, country
WHERE city.Population > country.Population
ORDER BY count(country.Name) DESC
GROUP BY city.Name, city.Population
LIMIT 10;
```

Custom # 2:

```
SELECT Name, Population
FROM Country
WHERE Name LIKE "A%"
ORDER BY Population DESC
LIMIT 10;
```

Bonus Custom:

```
SELECT COUNT(*) AS "# of Countries with 1 City"
FROM (SELECT CountryCode, COUNT(countryCode) AS "NumberOfCities" FROM city GROUP BY countryCode) AS CountryCodeTable
WHERE NumberOfCities = 1;
```


# WorldDatabaseQueries






Custom # 1

SELECT city.Name, city.Population, count(country.Name)
FROM city, country
WHERE city.Population > country.Population
ORDER BY count(country.Name) DESC
GROUP BY city.Name, city.Population
LIMT 10;



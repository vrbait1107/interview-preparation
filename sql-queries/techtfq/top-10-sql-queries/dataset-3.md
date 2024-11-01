
```sql

DROP TABLE car_travels;

CREATE TABLE car_travels
(
    cars                    VARCHAR(40),
    days                    VARCHAR(10),
    cumulative_distance     INT
);

INSERT INTO car_travels VALUES ('Car1', 'Day1', 50);
INSERT INTO car_travels VALUES ('Car1', 'Day2', 100);
INSERT INTO car_travels VALUES ('Car1', 'Day3', 200);
INSERT INTO car_travels VALUES ('Car2', 'Day1', 0);
INSERT INTO car_travels VALUES ('Car3', 'Day1', 0);
INSERT INTO car_travels VALUES ('Car3', 'Day2', 50);
INSERT INTO car_travels VALUES ('Car3', 'Day3', 50);
INSERT INTO car_travels VALUES ('Car3', 'Day4', 100);

```

1. From the given cars_travel table, find the actual distance travelled by each car corresponding to each day

```sql

SELECT *, 
cumulative_distance - LAG(cumulative_distance, 1, 0) OVER(PARTITION BY cars ORDER BY days) AS distance_travelled 
FROM car_travels;

```

---

2. **Calculate Daily Averages**: Write a query to calculate the average distance traveled per day by each car.

```sql

WITH CTE AS(
SELECT *, 
cumulative_distance - LAG(cumulative_distance, 1, 0) OVER(PARTITION BY cars ORDER BY days) as daily_distance
FROM car_travels
)

SELECT cars,
ROUND(AVG(daily_distance), 2) AS average
FROM CTE
GROUP BY cars;

```

---

3. **Find Maximum Distance**: Identify the car that traveled the maximum cumulative distance on a single day and return the car's name, the day, and the distance.

```sql

SELECT 
    cars, days, cumulative_distance
FROM
    car_travels
WHERE
    cumulative_distance IN (SELECT 
            MAX(cumulative_distance)
        FROM
            car_travels);

```

---

4. **Cumulative Distance Analysis**: Write a query that lists each car along with its cumulative distance traveled on the last day recorded in the table.

```sql


SELECT 
    cars, cumulative_distance
FROM
    car_travels c1
WHERE
    days = (SELECT 
            MAX(days)
        FROM
            car_travels c2
        WHERE
            c2.cars = c1.cars);
```

---

5. **Cumulative Growth**: Write a query that calculates the daily growth in distance traveled for each car, returning the day, car, previous day's distance, and current day's distance.

```sql

WITH CTE AS (
SELECT *, 
cumulative_distance - LAG(cumulative_distance, 1, 0) OVER(partition by cars) AS `current`
FROM car_travels
)

SELECT *, 
LAG(current, 1, 0) OVER(partition by cars) AS `previous`
FROM CTE;

```

6. **Rank Cars by Distance**: Create a query that ranks the cars based on their total cumulative distance traveled, returning the car name and its rank.

```sql


WITH CTE AS (
SELECT cars, MAX(cumulative_distance) as max_distance_by_car
FROM car_travels
group by cars
)

SELECT *, dense_rank() OVER(order by max_distance_by_car DESC) as `rank` FROM CTE;



```




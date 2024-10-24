

```sql

DROP TABLE IF EXISTS cars;

CREATE TABLE cars
(
	model_id		INT PRIMARY KEY,
	model_name		VARCHAR(100),
	color			VARCHAR(100),
	brand			VARCHAR(100)
);

INSERT INTO cars VALUES(1,'Leaf', 'Black', 'Nissan');
INSERT INTO cars VALUES(2,'Leaf', 'Black', 'Nissan');
INSERT INTO cars VALUES(3,'Model S', 'Black', 'Tesla');
INSERT INTO cars VALUES(4,'Model X', 'White', 'Tesla');
INSERT INTO cars VALUES(5,'Ioniq 5', 'Black', 'Hyundai');
INSERT INTO cars VALUES(6,'Ioniq 5', 'Black', 'Hyundai');
INSERT INTO cars VALUES(7,'Ioniq 6', 'White', 'Hyundai');


```

---

1. **Count the number of distinct car models for each brand.**

```sql

SELECT 
    brand, COUNT(DISTINCT model_name) AS distinct_model
FROM
    cars
GROUP BY brand;

```

---

2. **Identify any models that have duplicate entries (same `model_name`, `color`, and `brand`).**

```sql

SELECT 
    model_name, brand, color, COUNT(*)
FROM
    cars
GROUP BY model_name , brand , color
HAVING COUNT(*) > 1;

```
---


3. **List the colors available for each brand along with the count of each color.**

```sql

SELECT 
    brand, color, COUNT(*) AS count
FROM
    cars
GROUP BY brand , color;

```

---

4. **Find brands that offer more than one color of cars.**

```sql

SELECT 
    brand
FROM
    cars
GROUP BY brand
HAVING COUNT(DISTINCT color) > 1;

```

---


5. **Write a query to delete duplicate entries from the `cars` table, keeping only one instance of each.**

```sql

DELETE FROM cars 
WHERE
    model_id IN (SELECT 
        MAX(model_id)
    FROM
        cars
    GROUP BY model_name , brand
    HAVING COUNT(*) > 1);
    
WITH CTE AS (
SELECT *, 
    ROW_NUMBER() OVER(PARTITION BY model_name, brand) AS row_value
FROM
    cars
)

DELETE FROM CTE WHERE row_value > 1;

```

---

6. **Find all brands that have the model "Ioniq 5".**

```sql

SELECT DISTINCT brand
FROM cars
WHERE model_name = "Ioniq 5";

```

---

7. **Calculate the percentage of cars that are of each color in the table.**

```sql

SELECT 
    color,
    COUNT(*) AS color_count,
    (COUNT(*) / (SELECT 
            COUNT(*)
        FROM
            cars)) * 100 AS percentage
FROM
    cars
GROUP BY color;

```


---
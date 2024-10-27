```sql
DROP TABLE IF EXISTS travel_items;
CREATE TABLE travel_items
(
	id              INT,
	item_name       VARCHAR(50),
	total_count     INT
);

INSERT INTO travel_items VALUES (1, 'Water Bottle', 2);
INSERT INTO travel_items VALUES (2, 'Tent', 1);
INSERT INTO travel_items VALUES (3, 'Apple', 4);

```

1. **Ungroping Data**

```sql

WITH RECURSIVE CTE AS (
SELECT
    ID, 
    item_name, 
    total_count
FROM travel_items

UNION ALL 
SELECT 
    ID,
    item_name,
    total_count - 1
FROM CTE WHERE total_count > 1
)

SELECT ID, item_name FROM CTE ORDER BY ID, item_name;

```
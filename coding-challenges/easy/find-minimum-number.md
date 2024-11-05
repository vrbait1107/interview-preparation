## Find Minimum Number

### With Inbuilt Function

```php

<?php

function findMinimum(array $values): int
{
    return min($values);
}

echo findMinimum([12, 555, 5584, 1934, 84, 10, 374]);

?>

```

---

### Without Inbuilt Function

```php

<?php

function findMinimum(array $values): int
{
    $minimum = $values[0] ?? 0;

    foreach ($values as $value) {
        if ($value < $minimum) {
            $minimum = $value;
        }
    }

    return $minimum;
}

echo findMinimum([12, 555, 5584, 1934, 84, 10, 374]);

?>

```



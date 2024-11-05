## Find Maximum Number

### With Inbuilt Function

```php

<?php

function findMaximum(array $values): int
{
    return max($values);
}

echo findMaximum([12, 555, 5584, 8888, 1934, 84, 10, 374]);

?>

```

---

### Without Inbuilt Function

```php

<?php

function findMaximum(array $values): int
{
    $maximum = $values[0] ?? 0;

    foreach ($values as $value) {
        if ($value > $maximum) {
            $maximum = $value;
        }
    }

    return $maximum;
}

echo findMaximum([12, 555, 5584, 8888, 1934, 84, 10, 374]);


?>

```

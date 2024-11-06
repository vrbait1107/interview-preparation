## Array Count Values Implementation

### With Built in Function

```php

<?php

function arrayCountValuesBuiltIn(array $values) :array
{
    return array_count_values($values);
}

print_r(arrayCountValues([42, 7, 19, 88, 53, 61, 34, 12, 74, 29, 42, 19,
53, 88, 12, 34, 61, 29, 74, 7, 53, 42, 88, 19,61]));

?>

```

---

### Without Built in Function

```php

<?php

function arrayCountValues(array $values): array
{
    $countValues = [];

    foreach ($values as $value) {
        if (isset($countValues[$value])) {
            $countValues[$value]++;
        } else {
            $countValues[$value] = 1;
        }
    }

    return $countValues;
}

print_r(arrayCountValues([42, 7, 19, 88, 53, 61, 34, 12, 74, 29, 42, 19,
53, 88, 12, 34, 61, 29, 74, 7, 53, 42, 88, 19,61]));

```
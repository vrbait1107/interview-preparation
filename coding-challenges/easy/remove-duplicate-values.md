## Remove Duplicate Values from Array with and without inbuilt functions


### With Inbuilt Function

```php

<?php

function uniqueValues(array $values): array
{
    return array_unique($values);
}

print_r(uniqueValues(["Something", "Something", "Some", "Some", "Thing"]));

?>

```

---

### Without Inbuilt Function

```php

function uniqueValues(array $values): array
{
    $uniqueValues = [];

    foreach ($values as $value) {
        if (!in_array($value, $uniqueValues)) {
            $uniqueValues[] = $value;
        }
    }

    return $uniqueValues;
}

print_r(uniqueValues(["Something", "Something", "Some", "Some", "Thing"]));

?>

```



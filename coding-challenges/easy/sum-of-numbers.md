## Sum of Numbers


### With Inbuilt Function

```php

<?php

function sumOfNumbers(array $array): int
{
    return array_sum($array);
}

print_r(sumOfNumbers([4, 5, 6, 7, 8]));

```

---

### Without Inbuilt Function

```php

<?php

function sumOfNumbers(array $array): int
{
    $sum = 0;
    $count = count($array);

    for ($i = 0; $i < $count; $i++) {
        $sum += $array[$i];
    }

    return $sum;
}

print_r(sumOfNumbers([4, 5, 6, 7, 8]));

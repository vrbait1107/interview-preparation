## Sorting Desc

### Without Inbuilt Function

```php

<?php

$array = [4, 55, 33, 23, 56, 67, 223, 67];

$count = count($array);

for ($i = 0; $i < $count; $i++) {
    for ($j = 0; $j < $count - 1; $j++) {
        if ($array[$j] < $array[$j + 1]) {
            $temp = $array[$j];
            $array[$j] = $array[$j + 1];
            $array[$j + 1] = $temp;
        }
    }
}

print_r($array);

?>

```

---

### With Inbuilt Function

```php

<?php
$array = [4, 55, 33, 23, 56, 67, 223, 67];
rsort($array);
print_r($array);
?>

```

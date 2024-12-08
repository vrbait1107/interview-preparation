# Floyd’s Triangle Pattern

## Number Pattern

```

1 
2 3 
4 5 6 
7 8 9 10

```

```php

<?php
$rows = 4;
$n = 1;

for ($i = 1; $i <= $rows; $i++) {
    for ($j = 1; $j <= $i; $j++) {
        echo "$n ";
        $n++;
    }

    echo "\n";
}

?>

```

---

## Alphabet Pattern

```

A 
B C 
D E F 
G H I J 

```


```php

<?php
$rows = 4;
$n = 1;

for ($i = 1; $i <= $rows; $i++) {
    for ($j = 1; $j <= $i; $j++) {
        echo chr(64 + $n) . " ";
        $n++;
    }

    echo "\n";
}

?>

```

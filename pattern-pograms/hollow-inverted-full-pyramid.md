# Hollow Inverted Full Pyramid Pattern

## Star Pattern

```

* * * * * * * * * 
  *           * 
    *       * 
      *   * 
        * 
        
```

```php

<?php

$rows = 5;

for ($i = 5; $i >= 1; $i--) {
    echo str_repeat("  ", $rows - $i);

    for ($j = 1; $j <= $i * 2 - 1; $j++) {
        if ($j == 1 || $j == $i * 2 - 1 || $i == 1 || $i == 5) {
            echo "* ";
        } else {
            echo "  ";
        }
    }

    echo "\n";
}

?>

```

---

## Number Pattern

```

1 2 3 4 5 6 7 8 9 
  1           7 
    1       5 
      1   3 
        1

```

```php

<?php

$rows = 5;

for ($i = 5; $i >= 1; $i--) {
    echo str_repeat("  ", $rows - $i);

    for ($j = 1; $j <= $i * 2 - 1; $j++) {
        if ($j == 1 || $j == $i * 2 - 1 || $i == 1 || $i == 5) {
            echo "$j ";
        } else {
            echo "  ";
        }
    }

    echo "\n";
}

?>

```

---

## Alphabet Pattern


```

A B C D E F G H I 
  A           G 
    A       E 
      A   C 
        A 

```


```php

<?php

$rows = 5;

for ($i = 5; $i >= 1; $i--) {
    echo str_repeat("  ", $rows - $i);

    for ($j = 1; $j <= $i * 2 - 1; $j++) {
        if ($j == 1 || $j == $i * 2 - 1 || $i == 1 || $i == 5) {
            echo chr(64 + $j) . " ";
        } else {
            echo "  ";
        }
    }

    echo "\n";
}

?>

```
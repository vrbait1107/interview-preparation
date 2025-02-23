# 3X3 SQUARE MATRIX

## Number Pattern

```
1 2 3
4 5 6
7 8 9 
```

```php

<?php

for ($i = 1; $i <= 9; $i++) {
    echo "$i ";

    if ($i % 3 === 0) {
        echo "\n";
    }
}
?>

```

---

## Star Pattern


```
* * * 
* * * 
* * * 
```


```

<?php

for ($i = 1; $i <= 9; $i++) {
    echo "* ";

    if ($i % 3 === 0) {
        echo "\n";
    }
}
?>

```

---

## Alphabet Pattern

```
A B C 
D E F 
G H I
```

```php

<?php

for ($i = 1; $i <= 9; $i++) {
    echo chr(64 + $i) . " ";

    if ($i % 3 === 0) {
        echo "\n";
    }
}

?>

```
# Hourglass Pattern

## Star Pattern

```

* * * * * * * * * 
  * * * * * * * 
    * * * * * 
      * * * 
        * 
      * * * 
    * * * * * 
  * * * * * * * 
* * * * * * * * * 

```



```php

<?php
$rows = 5;

for ($i = 5; $i >= 1; $i--) {
    echo str_repeat("  ", $rows - $i);
    echo str_repeat("* ", 2 * $i - 1);
    echo "\n";
}

for ($i = 2; $i <= 5; $i++) {
    echo str_repeat("  ", $rows - $i);
    echo str_repeat("* ", 2 * $i - 1);
    echo "\n";
}

?>

```

---

## Number Pattern

```
1 2 3 4 5 6 7 8 9 
  1 2 3 4 5 6 7 
    1 2 3 4 5 
      1 2 3 
        1 
      1 2 3 
    1 2 3 4 5 
  1 2 3 4 5 6 7 
1 2 3 4 5 6 7 8 9 

```


```php

<?php
$rows = 5;

for ($i = 5; $i >= 1; $i--) {
    echo str_repeat("  ", $rows - $i);

    for ($j = 1; $j <= 2 * $i - 1; $j++) {
        echo "$j ";
    }
    echo "\n";
}

for ($i = 2; $i <= 5; $i++) {
    echo str_repeat("  ", $rows - $i);
    for ($j = 1; $j <= 2 * $i - 1; $j++) {
        echo "$j ";
    }
    echo "\n";
}

?>

```

---

## Alphabet Pattern

```
A B C D E F G H I 
  A B C D E F G 
    A B C D E 
      A B C 
        A 
      A B C 
    A B C D E 
  A B C D E F G 
A B C D E F G H I

```

```php

<?php
$rows = 5;

for ($i = 5; $i >= 1; $i--) {
    echo str_repeat("  ", $rows - $i);

    for ($j = 1; $j <= 2 * $i - 1; $j++) {
        echo chr(64 + $j) . " ";
    }
    echo "\n";
}

for ($i = 2; $i <= 5; $i++) {
    echo str_repeat("  ", $rows - $i);
    for ($j = 1; $j <= 2 * $i - 1; $j++) {
        echo chr(64 + $j) . " ";
    }
    echo "\n";
}

?>

```

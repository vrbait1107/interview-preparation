# Hollow Full Pyramid Pattern

In the Hollow Pyramid pattern, we only have to print the boundary of the full pyramid.

---

## Star Pattern

```
        * 
      *   * 
    *       * 
  *           * 
* * * * * * * * * 
```


```php

<?php

$rows = 5;

for ($i = 1; $i <= $rows; $i++) {
    echo str_repeat("  ", $rows - $i);

    for ($j = 1; $j <= $i * 2 - 1; $j++) {
        if ($i == 1 || $i == $rows || $j == 1 || $j == $i * 2 - 1) {
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
        1 
      1   3 
    1       5 
  1           7 
1 2 3 4 5 6 7 8 9 
```

```php

<?php

$rows = 5;

for ($i = 1; $i <= $rows; $i++) {
    echo str_repeat("  ", $rows - $i);

    for ($j = 1; $j <= $i * 2 - 1; $j++) {
        if ($i == 1 || $i == $rows || $j == 1 || $j == $i * 2 - 1) {
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
        A 
      A   C 
    A       E 
  A           G 
A B C D E F G H I 

```

```php

<?php

$rows = 5; 

for($i = 1; $i <= $rows; $i++){
  echo str_repeat("  ", $rows - $i);
 
 for($j = 1; $j <= ($i * 2 - 1); $j++){
  if($i == 1 || $i == $rows || $j == 1 || $j == ($i * 2 - 1)){
     echo chr(64 + $j) . " ";
   }else{
     echo "  ";
   }
   
 }
 
  echo "\n";
}


?>


```
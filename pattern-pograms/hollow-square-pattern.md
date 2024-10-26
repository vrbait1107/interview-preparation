# Hollow Square Pattern

The Hollow Square Pattern is a square with only the boundary lines. The space inside should be empty in this pattern.

---


## Star Pattern

```

* * * * * 
*       * 
*       * 
*       * 
* * * * * 

```


```php

<?php

$rows = 5;

for ($i = 1; $i <= $rows; $i++) {
    for ($j = 1; $j <= $rows; $j++) {
        if ($i == 1 || $i == $rows || $j == 1 || $j == $rows) {
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

1 2 3 4 5 
1       5 
1       5 
1       5 
1 2 3 4 5 

```

```php

<?php

$rows = 5;

for ($i = 1; $i <= $rows; $i++) {
    for ($j = 1; $j <= $rows; $j++) {
        if ($i == 1 || $i == $rows || $j == 1 || $j == $rows) {
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

A B C D E 
A       E 
A       E 
A       E 
A B C D E 

```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  
  for($j = 1; $j <= $rows; $j++){
    
    
    if($i == 1 || $i == $rows || $j == 1 || $j == $rows){
      echo chr(64 + $j) . " ";
    }else{
      echo "  ";
    }
    
  }
  
  echo "\n";

}

```
# Full Pyramid Pattern

## Star Pattern

```

        * 
      * * * 
    * * * * * 
  * * * * * * * 
* * * * * * * * * 

```

```php

$rows = 5; 

for($i = 1; $i <= $rows; $i++){
  echo str_repeat("  ", $rows - $i);
  echo str_repeat("* ", ($i * 2 - 1));
  echo "\n";
}

```

---

## Number Pattern

```

        1 
      1 2 3 
    1 2 3 4 5 
  1 2 3 4 5 6 7 
1 2 3 4 5 6 7 8 9 

```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  echo str_repeat("  ", $rows - $i);
  for($j = 1; $j <= (2 * $i - 1); $j++){
    echo "$j ";
  }
  
  echo "\n";
}

```

---

## Alphabet Pattern

```

        A 
      A B C 
    A B C D E 
  A B C D E F G 
A B C D E F G H I

```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  echo str_repeat("  ", $rows - $i);
  for($j = 1; $j <= (2 * $i - 1); $j++){
    echo chr(64 + $j)  . " ";
  }
  
  echo "\n";
}


```


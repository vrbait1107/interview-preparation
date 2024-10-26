# Rhombus Pattern

The Rhombus pattern is similar to the square pattern, just that we have to add spaces before each line and their count decreases progressively with rows.

---

## Star Pattern

```

    * * * * * 
   * * * * * 
  * * * * * 
 * * * * * 
* * * * * 

```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  echo str_repeat(" ", $rows - $i);
  echo str_repeat("* ", $rows);
  echo "\n";
}

```
---

## Number Pattern

```

    1 2 3 4 5 
   1 2 3 4 5 
  1 2 3 4 5 
 1 2 3 4 5 
1 2 3 4 5 

```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  echo str_repeat(" ", $rows - $i);
  
  for($j = 1; $j <= $rows; $j++){
    echo "$j ";
  }
  
  echo "\n";
}

```

---

## Aplphabet Pattern

```
    A B C D E 
   A B C D E 
  A B C D E 
 A B C D E 
A B C D E 
```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  echo str_repeat(" ", $rows - $i);
  
  for($j = 1; $j <= $rows; $j++){
    echo chr(64 + $j) . " ";
  }
  
  echo "\n";
}

```


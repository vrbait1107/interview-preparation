# Right Half Pyramid Pattern

## Star Pattern

```
*           
* *         
* * *       
* * * *     
* * * * *
```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  echo str_repeat("* ", $i);
  echo "\n";
}

```

---

## Number Pattern

```

1         
1 2
1 2 3
1 2 3 4
1 2 3 4 5 

```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  for($j = 1; $j <= $i; $j++){
    echo "$j ";
  }
  
  echo "\n";
}

```
---

## Alphabet Pattern

```

A
A B
A B C
A B C D
A B C D E

```

```php

$rows = 5;

for($i = 1; $i <= $rows; $i++){
  for($j = 1; $j <= $i; $j++){
    echo chr(64 + $j) . " ";
  }
  
  echo "\n";
}

```
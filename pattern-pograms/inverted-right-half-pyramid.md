# Inverted Right Half Pyramid Pattern

## Star Pattern

```

* * * * *
* * * *
* * *
* *
*

```

```php

$rows = 5;

for ($i = 1; $i <= $rows; $i++) {
   
   for ($j = 1; $j <= ($rows - $i + 1); $j++) {
      echo "* "; 
   }
   
   echo "\n";
}

```

## Number Pattern

```

1 2 3 4 5 
1 2 3 4 
1 2 3 
1 2 
1 

```


```php

$rows = 5; 

for ($i = 1; $i <= $rows; $i++) {
   
   for ($j = 1; $j <= ($rows - $i + 1); $j++) {
      echo "$j "; 
   }
   
   echo "\n";
}

```

## Alphabet Pattern

```

A B C D E 
A B C D 
A B C 
A B 
A 

```

```php

$rows = 5; 

for ($i = 1; $i <= $rows; $i++) {
   
   for ($j = 1; $j <= ($rows - $i + 1); $j++) {
      echo chr(64 + $j) . " "; 
   }
   
   echo "\n";
}

```
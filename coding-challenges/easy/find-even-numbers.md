## Find even numbers from array


```php

<?php

$array = [1, 4, 5, 6, 3, 44, 55, 34, 56, 345, 654, 43, 4553, 6534, 12, 23];

function findEvenNumbers(array $array) :array{
  
  $evenNumbers = [];
  
  foreach($array as $value){
    if($value % 2 === 0){
      $evenNumbers[] = $value;
    }
  }
  
  return $evenNumbers;
  
}

function findEvenNumbers(array $array) :array{
  return array_filter($array, fn($value) => $value % 2 === 0);
}

print_r(findEvenNumbers($array));

## Replace Empty Values with NULL

### With Inbuilt Function

```php

<?php

$array = [ 
    [0 => 1, 1 => 0, 2 => '', 3 => 'a'],
    [0 => 1, 1 => '', 2 => 0, 3 => 'b']
];


function replace(&$value){
  if($value === ""){
    $value = "NULL";
  }
}

array_walk_recursive($array, "replace");

print_r($array);

?>

```
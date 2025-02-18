
### Merge Key Value Pairs


### Without Built in Function

```php

<?php

/*

*INPUT *

  $array1 = [[77, 87], [23, 45]];

  $array2 = ["w3resource", "com"];
  

------------------------------------

* OUTPUT *

Array
(
    [0] => Array
        (
            [0] => 77
            [1] => 87
            [2] => w3resource
        )

    [1] => Array
        (
            [0] => 23
            [1] => 45
            [2] => com
        )

)

*/

function merge_arrays()
{
    $mergedArray = [];

    $array1 = [[77, 87], [23, 45]];

    $array2 = ["w3resource", "com"];

    foreach ($array1 as $key => $value) {
        if (isset($array2[$key])) {
          
          $value[] = $array2[$key];
          
            array_push($mergedArray,
                $value
            );
            
        }
    }

    print_r($mergedArray);
}

merge_arrays();

?>

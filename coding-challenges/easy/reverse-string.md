## Reverse String

### With Inbuilt Function

```php

<?php

$string = "Hello World";

function reverseString(string $string) :string{
  return strrev($string);
}

```

---

### Without Inbuilt Function

```php

function reverseString(string $string) :string{
  $length = strlen($string) - 1;
  
  $reversed = "";
  
  for($i = $length; $i >= 0; $i--){
    $reversed .= $string[$i];
  }
  
  return $reversed;
}

function reverseString(string $string): string
{
    return implode("", array_reverse(str_split($string)));
}

print_r(reverseString("Hello World"));

```




## How to check whether a string is a palindrome or not?

### With Inbuilt Function

```php

function isPalindrome(string $word) :bool {
  return strrev($word) === $word;
}

```

### Without Inbuilt Function

```php

function isPalindromeCustom(string $word):bool {
  $length = strlen($word) - 1;
  $reversed = '';

  for($i = $length; $i >= 0; $i--){
    $reversed .= $word[$i];
  }
  
  return $reversed === $word;
  
}

```
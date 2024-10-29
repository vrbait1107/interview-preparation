## Factorial Program With Recursion


```php

<?php

function factorialProgramRecusion(int $number): int
{
    if ($number == 1) {
        return 1;
    }

    return $number * factorialProgramRecusion($number - 1);
}

print_r(factorialProgramRecusion(3));

?>

```
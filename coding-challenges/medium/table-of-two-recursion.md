## Print Table of Two without Any Loop


```php

<?php

function tableOfTwoWithRecursion(int $number, int $count = 1): void
{
    if ($count > 10) {
        return;
    }

    echo $number * $count . "\n";

    $count++;

    tableOfTwoWithRecursion($number, $count);
}

tableOfTwoWithRecursion(2);

```
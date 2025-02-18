## Output Given String from Input String

```

INPUT: aaabbccccdeee
OUTPUT: a3b2c4e3

```

### Without Built in Function


```php

<?php

function countCharactersWithCount(string $word): string
{
    $countCharactersWithCount = customArrayCountValues($word);
    return makeStringWithKeyValues($countCharactersWithCount);
}

function makeStringWithKeyValues(array $array): string
{
    $concatedString = "";

    foreach ($array as $key => $value) {
        $concatedString .= $key;
        $concatedString .= $value;
    }

    return $concatedString;
}

function customArrayCountValues(string $word): array
{
    $length = strlen($word);
    $countValues = [];

    for ($i = 0; $i < $length; $i++) {
        if (isset($countValues[$word[$i]])) {
            $countValues[$word[$i]]++;
        } else {
            $countValues[$word[$i]] = 1;
        }
    }

    return $countValues;
}

print_r(countCharactersWithCount("aaabbccccdeee"));

```

### With Inbuilt Functions

```php

<?php

function countCharactersWithCount(string $word): string{
  $array = str_split($word);
  $countCharactersWithCount = array_count_values($array);
  return str_replace(["=", "&"], ["", ""], http_build_query($countCharactersWithCount)) . "\n";
}


print_r(countCharactersWithCount("aaabbccccdeee"));

?>

```

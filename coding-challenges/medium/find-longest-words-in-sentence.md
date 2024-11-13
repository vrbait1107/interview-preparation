## Program to find the longest word in a given sentence.

```php

<?php

function findLongestWords(string $sentence): array
{
    $words = explode(" ", $sentence);
    $maxLength = 0;
    $maxLengthWords = [];

    foreach ($words as $word) {
        if (strlen($word) > $maxLength) {
            $maxLength = strlen($word);
            $maxLengthWords = [$word];
        } elseif (strlen($word) === $maxLength) {
            $maxLengthWords[] = $word;
        }
    }

    return $maxLengthWords;
}

print_r(
    findLongestWords(
        "The cat stared out the window, pondering the mysteries of the passing clouds."
    )
);

?>

```
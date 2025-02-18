## Find Second Highest Salary

### With Inbuilt Functions

```php

<?php

function secondHighestSalary(array $salaries):int{
  rsort($salaries);
  return $salaries[1];
}

```

---

### Without Inbuilt Functions

```php

<?php

function secondHighestSalary(array $salaries):int{
  $max = highestSalary($salaries);
  $secondMax = 0;
  
  foreach($salaries as $salary){
    if($salary > $secondMax && $salary != $max){
      $secondMax = $salary;
    }
  }
  
  return $secondMax;
}

function highestSalary(array $salaries):int{
  $max = 0;
  
  foreach($salaries as $salary){
    if($salary > $max){
      $max = $salary;
    }
  }
  
  return $max;
}

$salaries = [1000, 5000, 3000, 4000, 2000, 6000];
print_r(secondHighestSalary($salaries));

?>

```
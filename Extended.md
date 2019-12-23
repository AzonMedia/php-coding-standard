# Azonmedia Extended coding style guide

## Introduction

The extended coding style guide follows [PSR-12](https://www.php-fig.org/psr/psr-12/) with certain modifications.

## Differences to PSR-12
- example (from PSR-12) with modified opening { rule (and naming but this is described in Basic coding standard):
```php
<?php

declare(strict_types=1);

namespace Vendor\Package;

class ReturnTypeVariations
{
    public function function_name(int $arg1, $arg2): string
    {
        return 'foo';
    }

    public function another_function(
        string $foo,
        string $bar,
        int $baz
    ): string
    { //this brace goes here
        return 'foo';
    }
}
```
- control sructures when split on multiple lines:
```php
<?php

if (
    $expr1
    &&
    $expr2 //does not stay on the same line with the logical operator
) {
    // if body
} elseif (
    $expr3
    &&
    $expr4 //does not stay on the same line with the logical operator
) {
    // elseif body
}
```
- closure opening brace should be on the next line:
```php
$closure = function ($arg1, $arg2) use ($var1, $var2): bool
{
    // body
};
```
- do/while multiline:
```php
<?php

do {
    // structure body;
} while (
    $expr1
    &&
    $expr2
);
```
# Azonmedia Coding Style Guide

## Introduction

This guide follows [PSR-2](https://www.php-fig.org/psr/psr-2/) with certain differences.

## Differences to PSR-2
- the files must always contain `declare(strict_types=1);` on the second line after <?php
- lines should not exceed 180 characters
- true, false, null must be CAPS
- implements may go on next line and each interface being implemented may go on the next line
- methods must have type declaration for each argument. If the argument is of type mixed the declaration must be in a comment. Other type suggestions are acceptable in a comment section. In the comment it is acceptable to describe the allowed types separated with a pipe. Example:
```php
public abstract function method_1(int $arg1, /* scalar */ $arg2, /* mixed */ $arg3, /* resource */ $arg4) : void;
public abstract function method_2(?Some\Class1 $arg1 = NULL, /* Another\Class2 | int | NULL */ $arg2) : /* mixed */
```
- the methods must always have return type - be it a PHP supported type or a type in a comment. __construct(), __destruct() and __clone() are exceptions
- the closures must declare argument types and return types like methods
- the placement of the opening { on closures follows the rules for methods:
```php
$closure = function (string $arg1, /* mixed */ $arg2) : void
{
};
```

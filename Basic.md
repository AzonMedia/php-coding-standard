# Azonmedia Basic Coding Standard

## Introduction

The basic coding standard follows [PSR-1](https://www.php-fig.org/psr/psr-1/) with certain differences/exceptions.

## Differences to PSR-1

- namespaces - follow Vendor\Model convention and use PascalCase
- class names - follow PascalCase. Both class names and namespaces if contain abbreviation (like HTTP) should be named HttpRequest (vs HTTPRequest)
- properties - must be named like $snake_case for both static and dynamic properties
- methods - the methods must be named snake_case()
- **an exception to the naming of the methods is that if the class is extending a class that uses different naming convention (like the internal PHP classes which use camelCase) the extending class should use the same convention as the parent class**

## Additional rules

- the arguments and local variables must be in $snake_case. No variables should start with _.
- the only exception to the above rule is when the argument or the local variable is a reference (but not a reference to an object!). Example:
```php
public abstract function method_1(string $arg1, int &$_arg2, Some\Orm\Class1 &$object) : void;
```
```php
foreach ($rows as &$_row) {
    $_row['col'] = 55;
}
```
- variables that contain abbreviations must be named like $http_request (vs $HTTP_request)
- an exception to the rule of variables naming is for static variables containing runtime configuration. Example:
```php
class C1
{
    public const CONFIG_DEFAULT = ['prop1' => 55];
    public static $CONFIG_RUNTIME = [];
}
```
- Long methods should have a comment after the closing parenthesis `} /* end some_long_method() */`
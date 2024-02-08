Pattern: Use of `$this` in static method

Issue: -

## Description

Checks for usage of `$this` in static methods, which will cause runtime errors.

## Example

Example of **incorrect** code:

``` php
class SomeClass
{
    static function test()
    {
		return $this->$staticMember;
    }
}
```

Example of **correct** code:

```php
class SomeClass
{
    static function test()
    {
        return self::$staticMember;
    }
}
```

## Further Reading

* [PHP_CodeSniffer - Squiz.Scope.StaticThisUsage](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Scope/StaticThisUsageSniff.php)
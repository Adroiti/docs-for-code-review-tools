Pattern: Use of dynamic function call

Issue: -

## Description

Enforces that certain functions are not dynamically called. Example:

``` php
  $func = 'func_num_args';
  $func();
```


## Further Reading

* [WordPressVIPMinimum.Functions.DynamicCalls](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Functions/DynamicCallsSniff.php)
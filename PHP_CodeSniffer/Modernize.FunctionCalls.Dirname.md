Pattern: Use of `dirname()`

Issue: -

## Description

This rule will detect and auto-fix two typical code modernizations which can be made related to the `dirname()` function:
1. Since PHP 5.3, calls to `dirname(__FILE__)` can be replaced by `__DIR__`.
    Errorcode: `Modernize.FunctionCalls.Dirname.FileConstant`.
2. Since PHP 7.0, nested function calls to `dirname()` can be changed to use the `$levels` parameter.
    Errorcode: `Modernize.FunctionCalls.Dirname.Nested`.

## Further Reading

* [Modernize.FunctionCalls.Dirname](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#modernize)
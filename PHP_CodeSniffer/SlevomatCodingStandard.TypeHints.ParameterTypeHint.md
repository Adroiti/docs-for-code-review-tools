Pattern: Malformed parameter type hint

Issue: -

## Description

Checks for missing parameter typehints in case they can be declared natively. If the phpDoc contains something that can be written as a native PHP 7.0+ typehint, this rule reports that.
Checks for useless `@param` annotations. If the native method declaration contains everything and the phpDoc does not add anything useful, it's reported as useless and can optionally be automatically removed with `phpcbf`.
Forces to specify what's in traversable types like `array`, `iterable` and `\Traversable`.

Rule provides the following settings:

* `enableObjectTypeHint`: enforces to transform `@param object` into native `object` typehint. It's on by default if you're on PHP 7.2+
* `enableMixedTypeHint`: enforces to transform `@param mixed` into native `mixed` typehint. It's on by default if you're on PHP 8.0+
* `enableUnionTypeHint`: enforces to transform `@param string|int` into native `string|int` typehint. It's on by default if you're on PHP 8.0+
* `enableIntersectionTypeHint`: enforces to transform `@param Foo&Bar` into native `Foo&Bar` typehint. It's on by default if you're on PHP 8.1+
* `enableStandaloneNullTrueFalseTypeHints`: enforces to transform `@param true`, `@param false` or `@param null` into native typehints. It's on by default if you're on PHP 8.2+
* `traversableTypeHints`: enforces which typehints must have specified contained type. E.g. if you set this to `\Doctrine\Common\Collections\Collection`, then `\Doctrine\Common\Collections\Collection` must always be supplied with the contained type: `\Doctrine\Common\Collections\Collection|Foo[]`.

This rule can cause an error if you're overriding or implementing a parent method which does not have typehints. In such cases add `@phpcsSuppress SlevomatCodingStandard.TypeHints.ParameterTypeHint.MissingNativeTypeHint` annotation to the method to have this rule skip it.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.TypeHints.ParameterTypeHint](https://github.com/slevomat/coding-standard/blob/master/doc/type-hints.md#slevomatcodingstandardtypehintsparametertypehint-)
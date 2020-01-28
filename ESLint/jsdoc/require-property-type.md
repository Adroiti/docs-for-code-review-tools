Pattern: Missing `type` for `@property`

Issue: -

## Description

Requires that each `@property` tag has a `type` value.

|||
|---|---|
|Context|everywhere|
|Tags|N/A|

The following patterns are considered problems:

````js
/**
 * @typedef {SomeType} SomeTypedef
 * @property foo
 */
// Message: Missing JSDoc @property "foo" type.

/**
 * @typedef {SomeType} SomeTypedef
 * @prop foo
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":"prop"}}}
// Message: Missing JSDoc @prop "foo" type.

/**
 * @typedef {SomeType} SomeTypedef
 * @property foo
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":false}}}
// Message: Unexpected tag `@property`
````

The following patterns are not considered problems:

````js
/**
 * @typedef {SomeType} SomeTypedef
 */

/**
 * @typedef {SomeType} SomeTypedef
 * @property {number} foo
 */

/**
 * @namespace {SomeType} SomeName
 * @property {number} foo
 */

/**
 * @class
 * @property {number} foo
 */
````


<a name="eslint-plugin-jsdoc-rules-require-returns-check"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-property-type](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-property-type)

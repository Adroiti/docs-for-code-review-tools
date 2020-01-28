Pattern: Missing `@property` for `@typedef`/`@namespace`

Issue: -

## Description

Requires that all `@typedef` and `@namespace` tags have `@property`
when their type is a plain `object`, `Object`, or `PlainObject`.

Note that if any other type, including a subtype of object such as
`object<string, string>`, will not be reported.

<a name="eslint-plugin-jsdoc-rules-require-property-fixer-1"></a>
#### Fixer

The fixer for `require-example` will add an empty `@property`.

|||
|---|---|
|Context|Everywhere|
|Tags|`typedef`, `namespace`|

The following patterns are considered problems:

````js
/**
 * @typedef {object} SomeTypedef
 */
// Message: Missing JSDoc @property.

/**
 * @typedef {PlainObject} SomeTypedef
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":"prop"}}}
// Message: Missing JSDoc @prop.

/**
 * @namespace {Object} SomeName
 */
// Message: Missing JSDoc @property.
````

The following patterns are not considered problems:

````js
/**
 *
 */

/**
 * @property
 */

/**
 * @typedef {Object} SomeTypedef
 * @property {SomeType} propName Prop description
 */

/**
 * @typedef {object} SomeTypedef
 * @prop {SomeType} propName Prop description
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":"prop"}}}

/**
 * @typedef {object} SomeTypedef
 * @property
 * // arbitrary property content
 */

/**
 * @typedef {object<string, string>} SomeTypedef
 */

/**
 * @typedef {string} SomeTypedef
 */

/**
 * @namespace {object} SomeName
 * @property {SomeType} propName Prop description
 */

/**
 * @namespace {object} SomeName
 * @property
 * // arbitrary property content
 */

/**
 * @typedef {object} SomeTypedef
 * @property someProp
 * @property anotherProp This with a description
 * @property {anotherType} yetAnotherProp This with a type and desc.
 */
function quux () {

}
````


<a name="eslint-plugin-jsdoc-rules-require-property-description"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-property](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-property)

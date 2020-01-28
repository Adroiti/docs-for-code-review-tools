Pattern: Missing hyphen before `@param` description

Issue: -

## Description

Requires a hyphen before the `@param` description.

<a name="eslint-plugin-jsdoc-rules-require-hyphen-before-param-description-options-18"></a>
#### Options

This rule takes one optional string argument and an optional options object.

If the string is `"always"` then a problem is raised when there is no hyphen
before the description. If it is `"never"` then a problem is raised when there
is a hyphen before the description. The default value is `"always"`.

The options object may have the following properties:

- `checkProperties` - Boolean on whether to also apply the rule to `@property`
  tags.

|||
|---|---|
|Context|everywhere|
|Tags|`param` and optionally `property`|
|Aliases|`arg`, `argument`; optionally `prop`|
|Options|(a string matching `"always"|"never"`) and an optional object with a `checkProperties` property|

The following patterns are considered problems:

````js
/**
 * @param foo Foo.
 */
function quux () {

}
// Options: ["always"]
// Message: There must be a hyphen before @param description.

/**
 * @param foo Foo.
 */
function quux () {

}
// Message: There must be a hyphen before @param description.

/**
 * @param foo - Foo.
 */
function quux () {

}
// Options: ["never"]
// Message: There must be no hyphen before @param description.

/**
 * @param foo - foo
 * @param foo foo
 */
function quux () {

}
// Options: ["always"]
// Message: There must be a hyphen before @param description.

/**
 * @param foo foo
 * bar
 * @param bar - bar
 */
function quux () {

}
// Options: ["always"]
// Message: There must be a hyphen before @param description.

/**
 * @param foo
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"param":false}}}
// Message: Unexpected tag `@param`

/**
 * @typedef {SomeType} ATypeDefName
 * @property foo Foo.
 */
// Options: ["always",{"checkProperties":true}]
// Message: There must be a hyphen before @property description.

/**
 * @typedef {SomeType} ATypeDefName
 * @property foo - Foo.
 */
// Options: ["never",{"checkProperties":true}]
// Message: There must be no hyphen before @property description.
````

The following patterns are not considered problems:

````js
/**
 * @param foo - Foo.
 */
function quux () {

}
// Options: ["always"]

/**
 * @param foo Foo.
 */
function quux () {

}
// Options: ["never"]

/**
 * @param foo
 */
function quux () {

}

/**
 * @typedef {SomeType} ATypeDefName
 * @property foo - Foo.
 */
// Options: ["always",{"checkProperties":true}]

/**
 * @typedef {SomeType} ATypeDefName
 * @property foo Foo.
 */
// Options: ["never",{"checkProperties":true}]
````


<a name="eslint-plugin-jsdoc-rules-require-jsdoc"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-hyphen-before-param-description](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-hyphen-before-param-description)

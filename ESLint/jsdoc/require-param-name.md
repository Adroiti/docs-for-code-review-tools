Pattern: Missing `@param` name

Issue: -

## Description

Requires that all function parameters have names.

> The `@param` tag requires you to specify the name of the parameter you are documenting. You can also include the parameter's type, enclosed in curly brackets, and a description of the parameter.
>
> [JSDoc](https://jsdoc.app/tags-param.html#overview)

<a name="eslint-plugin-jsdoc-rules-require-param-name-options-21"></a>
#### Options

<a name="eslint-plugin-jsdoc-rules-require-param-name-options-21-contexts-5"></a>
##### <code>contexts</code>

Set this to an array of strings representing the AST context
where you wish the rule to be applied.
Overrides the default contexts (see below). Set to `"any"` if you want
the rule to apply to any jsdoc block throughout your files (as is necessary
for finding function blocks not attached to a function declaration or
expression, i.e., `@callback` or `@function` (or its aliases `@func` or
`@method`) (including those associated with an `@interface`).

|||
|---|---|
|Context|`ArrowFunctionExpression`, `FunctionDeclaration`, `FunctionExpression`; others when `contexts` option enabled|
|Tags|`param`|
|Aliases|`arg`, `argument`|
|Options|`contexts`|

The following patterns are considered problems:

````js
/**
 * @param
 */
function quux (foo) {

}
// Message: There must be an identifier after @param type.

/**
 * @param {string}
 */
function quux (foo) {

}
// Message: There must be an identifier after @param tag.

/**
 * @param {string}
 */
function quux (foo) {

}
// Options: [{"contexts":["any"]}]
// Message: There must be an identifier after @param tag.

/**
 * @function
 * @param {string}
 */
// Options: [{"contexts":["any"]}]
// Message: There must be an identifier after @param tag.

/**
 * @callback
 * @param {string}
 */
// Options: [{"contexts":["any"]}]
// Message: There must be an identifier after @param tag.

/**
 * @param foo
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"param":false}}}
// Message: Unexpected tag `@param`
````

The following patterns are not considered problems:

````js
/**
 * @param foo
 */
function quux (foo) {

}

/**
 * @param foo
 */
function quux (foo) {

}
// Options: [{"contexts":["any"]}]

/**
 * @param {string} foo
 */
function quux (foo) {

}

/**
 * @function
 * @param
 */

/**
 * @callback
 * @param
 */
````


<a name="eslint-plugin-jsdoc-rules-require-param-type"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-param-name](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-param-name)

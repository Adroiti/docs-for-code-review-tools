Pattern: Use of `@implements` on non-constructor function

Issue: -

## Description

Reports an issue with any non-constructor function using `@implements`.

Constructor functions, whether marked with `@class`, `@constructs`, or being
an ES6 class constructor, will not be flagged.

To indicate that a function follows another function's signature, one might
instead use `@type` to indicate the `@function` or `@callback` to which the
funciton is adhering.

<a name="eslint-plugin-jsdoc-rules-implements-on-classes-options-9"></a>
#### Options

<a name="eslint-plugin-jsdoc-rules-implements-on-classes-options-9-contexts"></a>
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
|Tags|`implements` (prevented)|
|Options|`contexts`|

The following patterns are considered problems:

````js
/**
 * @implements {SomeClass}
 */
function quux () {

}
// Message: @implements used on a non-constructor function

/**
 * @implements {SomeClass}
 */
function quux () {

}
// Options: [{"contexts":["any"]}]
// Message: @implements used on a non-constructor function

/**
 * @function
 * @implements {SomeClass}
 */
function quux () {

}
// Options: [{"contexts":["any"]}]
// Message: @implements used on a non-constructor function

/**
 * @callback
 * @implements {SomeClass}
 */
// Options: [{"contexts":["any"]}]
// Message: @implements used on a non-constructor function

/**
 * @implements {SomeClass}
 */
function quux () {

}
// Settings: {"jsdoc":{"tagNamePreference":{"implements":false}}}
// Message: Unexpected tag `@implements`
````

The following patterns are not considered problems:

````js
/**
 * @implements {SomeClass}
 * @class
 */
function quux () {

}

/**
 * @implements {SomeClass}
 * @class
 */
function quux () {

}
// Options: [{"contexts":["any"]}]

/**
 * @implements {SomeClass}
 */
// Options: [{"contexts":["any"]}]

/**
 * @implements {SomeClass}
 * @constructor
 */
function quux () {

}

/**
 *
 */
class quux {
  /**
   * @implements {SomeClass}
   */
  constructor () {

  }
}

/**
 *
 */
const quux = class {
  /**
   * @implements {SomeClass}
   */
  constructor () {

  }
}

/**
 *
 */
function quux () {

}

/**
 *
 */
function quux () {

}
// Settings: {"jsdoc":{"tagNamePreference":{"implements":false}}}

/**
 * @function
 * @implements {SomeClass}
 */

/**
 * @callback
 * @implements {SomeClass}
 */
````


<a name="eslint-plugin-jsdoc-rules-match-description"></a>

## Further Reading

* [eslint-plugin-jsdoc - implements-on-classes](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#implements-on-classes)

Pattern: Invalid JSDoc indentation

Issue: -

## Description

Reports invalid padding inside JSDoc blocks.

Ignores parts enclosed in Markdown "code block"'s. For example,
the following description is not reported:

```js
/**
 * Some description:
 * ```html
 * <section>
 *   <title>test</title>
 * </section>
 * ```
 */
```

<a name="eslint-plugin-jsdoc-rules-check-indentation-options-2"></a>
#### Options

This rule has an object option.

<a name="eslint-plugin-jsdoc-rules-check-indentation-options-2-excludetags"></a>
##### <code>excludeTags</code>

Array of tags (e.g., `['example', 'description']`) whose content will be
"hidden" from the `check-indentation` rule. Defaults to `['example']`.

By default, the whole JSDoc block will be checked for invalid padding.
That would include `@example` blocks too, which can get in the way
of adding full, readable examples of code without ending up with multiple
linting issues.

When disabled (by passing `excludeTags: []` option), the following code *will*
report a padding issue:

```js
/**
 * @example
 * anArray.filter((a) => {
 *   return a.b;
 * });
 */
```

|||
|---|---|
|Context|everywhere|
|Tags|N/A|
|Options| `excludeTags` |

The following patterns are considered problems:

````js
/**  foo */
function quux () {

}
// Message: There must be no indentation.

/**
 * foo
 *
 * @param bar
 *  baz
 */
function quux () {

}
// Message: There must be no indentation.

/**
 * Foo
 *   bar
 */
class Moo {}
// Message: There must be no indentation.

/**
 * foo
 *
 * @example
 * anArray.filter((a) => {
 *   return a.b;
 * });
 */
function quux () {

}
// Options: [{"excludeTags":[]}]
// Message: There must be no indentation.

/**
 * foo
 *
 * @example
 *   aaaa
 * @returns
 *   eeee
 */
function quux () {

}
// Message: There must be no indentation.

/**
 * foo
 * ```html
 * <section>
 *   <title>test</title>
 * </section>
 * ```
 * @returns
 *   eeee
 */
function quux () {

}
// Message: There must be no indentation.

/**
 * foo
 * ```   aaaa```
 * @returns
 *   eeee
 */
function quux () {

}
// Message: There must be no indentation.

/**
* @example <caption>
* Here is a long
*   indented summary of this
* example
* </caption>
* ```js
* function hi () {
*   alert('Hello');
* }
* ```
*/
// Options: [{"excludeTags":[]}]
// Message: There must be no indentation.

/**
* @example <caption>
* Here is a long
* summary of this
* example
* </caption>
* // Code is not wrapped into fenced code block
* function hi () {
*   alert('Hello');
* }
*/
// Options: [{"excludeTags":[]}]
// Message: There must be no indentation.
````

The following patterns are not considered problems:

````js
/**
 * foo
 *
 * @param bar
 * baz
 */
function quux () {

}

/*** foo */
function quux () {

}

/**
 * foo
 *
 * @example
 * anArray.filter((a) => {
 *   return a.b;
 * });
 */
function quux () {

}

/**
 * foo
 *
 * @example
 * anArray.filter((a) => {
 *   return a.b;
 * });
 * @returns
 *   eeee
 */
function quux () {

}
// Options: [{"excludeTags":["example","returns"]}]

/**
 * foo
 * ```html
 * <section>
 *   <title>test</title>
 * </section>
 * ```
 * @returns eeee
 */
function quux () {

}

/**
 * foo
 * ```   aaaa```
 * @returns eeee
 */
function quux () {

}

/**
* @example <caption>
* Here is a long
* summary of this
* example
* </caption>
* ```js
* function hi () {
*   alert('Hello');
* }
* ```
*/
// Options: [{"excludeTags":[]}]
````


<a name="eslint-plugin-jsdoc-rules-check-param-names"></a>

## Further Reading

* [eslint-plugin-jsdoc - check-indentation](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#check-indentation)

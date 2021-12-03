Pattern: Malformed multi-line JSDoc block

Issue: -

## Description

Controls how and whether jsdoc blocks can be expressed as single or multiple line blocks.

Note that if you set `noSingleLineBlocks` and `noMultilineBlocks` to `true` and configure them in a certain manner, you might effectively be prohibiting all jsdoc blocks!

Also allows for preventing text at the very beginning or very end of blocks.

The following patterns are considered problems:

```js
/** Reported up here
 * because the rest is multiline
 */
// Message: Should have no text on the "0th" line (after the `/**`).

/** Reported up here
 * because the rest is multiline
 */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noZeroLineText":true}]
// Message: Should have no text on the "0th" line (after the `/**`).

/** @abc {aType} aName Reported up here
 * because the rest is multiline
 */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noZeroLineText":true}]
// Message: Should have no text on the "0th" line (after the `/**`).

/** @tag */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noSingleLineBlocks":true}]
// Message: Single line blocks are not permitted by your configuration.

/** @tag {someType} */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noSingleLineBlocks":true}]
// Message: Single line blocks are not permitted by your configuration.

/** @tag {someType} aName */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noSingleLineBlocks":true}]
// Message: Single line blocks are not permitted by your configuration.

/** @tag */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noSingleLineBlocks":true,"singleLineTags":["someOtherTag"]}]
// Message: Single line blocks are not permitted by your configuration.
```

The following patterns are not considered problems:

```js
/** Not reported */

/**
 *  Not reported
 */

/** Reported up here
 * because the rest is multiline
 */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noZeroLineText":false}]

/** @tag */

/** @lends */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noSingleLineBlocks":true}]

/** @tag */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noSingleLineBlocks":true,"singleLineTags":["tag"]}]

/** @tag */
// "jsdoc/multiline-blocks": ["error"|"warn", {"noSingleLineBlocks":true,"singleLineTags":["*"]}]
```

## Further Reading

* [eslint-plugin-jsdoc - multiline-blocks](https://github.com/gajus/eslint-plugin-jsdoc#eslint-plugin-jsdoc-rules-multiline-blocks)
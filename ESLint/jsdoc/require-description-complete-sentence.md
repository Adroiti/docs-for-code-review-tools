Pattern: Missing complete sentence for description

Issue: -

## Description

Requires that block description, explicit `@description`, and `@param`/`@returns`
tag descriptions are written in complete sentences, i.e.,

* Description must start with an uppercase alphabetical character.
* Paragraphs must start with an uppercase alphabetical character.
* Sentences must end with a period.
* Every line in a paragraph (except the first) which starts with an uppercase
  character must be preceded by a line ending with a period.
* A colon or semi-colon followed by two line breaks is still part of the
  containing paragraph (unlike normal dual line breaks).
* Text within inline tags `{...}` are not checked for sentence divisions.
* Periods after items within the `abbreviations` option array are not treated
  as sentence endings.

<a name="eslint-plugin-jsdoc-rules-require-description-complete-sentence-options-14"></a>
#### Options

<a name="eslint-plugin-jsdoc-rules-require-description-complete-sentence-options-14-tags-2"></a>
##### <code>tags</code>

If you want additional tags to be checked for their descriptions, you may
add them within this option.

```js
{
  'jsdoc/require-description-complete-sentence': ['error', {tags: ['see', 'copyright']}]
}
```

The tags `@param`/`@arg`/`@argument` and `@property`/`@prop` will be properly
parsed to ensure that the checked "description" text includes only the text
after the name.

All other tags will treat the text following the tag name, a space, and
an optional curly-bracketed type expression (and another space) as part of
its "description" (e.g., for `@returns {someType} some description`, the
description is `some description` while for `@some-tag xyz`, the description
is `xyz`).

<a name="eslint-plugin-jsdoc-rules-require-description-complete-sentence-options-14-abbreviations"></a>
##### <code>abbreviations</code>

You can provide an `abbreviations` options array to avoid such strings of text
being treated as sentence endings when followed by dots. The `.` is not
necessary at the end of the array items.

|||
|---|---|
|Context|everywhere|
|Tags|doc block, `param`, `returns`, `description`, `property`, `summary`, `file`, `classdesc`, `todo`, `deprecated`, `throws`, 'yields' and others added by `tags`|
|Aliases|`arg`, `argument`, `return`, `desc`, `prop`, `fileoverview`, `overview`, `exception`, `yield`|
|Options|`tags`, `abbreviations`|
The following patterns are considered problems:

````js
/**
 * foo.
 */
function quux () {

}
// Message: Sentence should start with an uppercase character.

/**
 * foo?
 */
function quux () {

}
// Message: Sentence should start with an uppercase character.

/**
 * @description foo.
 */
function quux () {

}
// Message: Sentence should start with an uppercase character.

/**
 * Foo)
 */
function quux () {

}
// Message: Sentence must end with a period.

/**
 * `foo` is a variable
 */
function quux () {

}
// Message: Sentence must end with a period.

/**
 * Foo.
 *
 * foo.
 */
function quux () {

}
// Message: Sentence should start with an uppercase character.

/**
 * тест.
 */
function quux () {

}
// Message: Sentence should start with an uppercase character.

/**
 * Foo
 */
function quux () {

}
// Message: Sentence must end with a period.

/**
 * Foo
 * Bar.
 */
function quux () {

}
// Message: A line of text is started with an uppercase character, but preceding line does not end the sentence.

/**
 * Foo.
 *
 * @param foo foo.
 */
function quux (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * Foo.
 *
 * @param foo bar
 */
function quux (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * {@see Foo.bar} buz
 */
function quux (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * Foo.
 *
 * @returns {number} foo
 */
function quux (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * Foo.
 *
 * @returns foo.
 */
function quux (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * lorem ipsum dolor sit amet, consectetur adipiscing elit. pellentesque elit diam,
 * iaculis eu dignissim sed, ultrices sed nisi. nulla at ligula auctor, consectetur neque sed,
 * tincidunt nibh. vivamus sit amet vulputate ligula. vivamus interdum elementum nisl,
 * vitae rutrum tortor semper ut. morbi porta ante vitae dictum fermentum.
 * proin ut nulla at quam convallis gravida in id elit. sed dolor mauris, blandit quis ante at,
 * consequat auctor magna. duis pharetra purus in porttitor mollis.
 */
function longDescription (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * @arg {number} foo - Foo
 */
function quux (foo) {

}
// Message: Sentence must end with a period.

/**
 * @argument {number} foo - Foo
 */
function quux (foo) {

}
// Message: Sentence must end with a period.

/**
 * @return {number} foo
 */
function quux (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * Returns bar.
 *
 * @return {number} bar
 */
function quux (foo) {

}
// Message: Sentence should start with an uppercase character.

/**
 * @throws {object} Hello World
 * hello world
*/
// Message: Sentence must end with a period.

/**
 * @summary Foo
 */
function quux () {

}
// Message: Sentence must end with a period.

/**
 * @throws {SomeType} Foo
 */
function quux () {

}
// Message: Sentence must end with a period.

/**
 * @see Foo
 */
function quux () {

}
// Options: [{"tags":["see"]}]
// Message: Sentence must end with a period.

/**
 * @param foo Foo bar
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"description":false}}}
// Options: [{"tags":["param"]}]
// Message: Sentence must end with a period.

/**
 * Sorry, but this isn't a complete sentence, Mr.
 */
function quux () {

}
// Options: [{"abbreviations":["Mr"]}]
// Message: Sentence must end with a period.

/**
 * Sorry, but this isn't a complete sentence Mr.
 */
function quux () {

}
// Options: [{"abbreviations":["Mr."]}]
// Message: Sentence must end with a period.

/**
 * Sorry, but this isn't a complete sentence Mr. 
 */
function quux () {

}
// Options: [{"abbreviations":["Mr"]}]
// Message: Sentence must end with a period.

/**
 * Sorry, but this isn't a complete sentence Mr. and Mrs.
 */
function quux () {

}
// Options: [{"abbreviations":["Mr","Mrs"]}]
// Message: Sentence must end with a period.

/**
 * This is a complete sentence. But this isn't, Mr.
 */
function quux () {

}
// Options: [{"abbreviations":["Mr"]}]
// Message: Sentence must end with a period.

/**
 * This is a complete Mr. sentence. But this isn't, Mr.
 */
function quux () {

}
// Options: [{"abbreviations":["Mr"]}]
// Message: Sentence must end with a period.

/**
 * This is a complete Mr. sentence.
 */
function quux () {

}
// Message: Sentence should start with an uppercase character.

/**
 * This is fun, i.e. enjoyable, but not superlatively so, e.g. not
 * super, wonderful, etc..
 */
function quux () {

}
// Message: Sentence should start with an uppercase character.

/**
 * Do not have dynamic content; e.g. homepage. Here a simple unique id
 * suffices.
 */
 function quux () {

 }
// Message: Sentence should start with an uppercase character.
````

The following patterns are not considered problems:

````js
/**
 * @param foo - Foo.
 */
function quux () {

}

/**
 * Foo.
 */
function quux () {

}

/**
 * Foo.
 * Bar.
 */
function quux () {

}

/**
 * Foo.
 *
 * Bar.
 */
function quux () {

}

/**
 * Тест.
 */
function quux () {

}

/**
 * Foo
 * bar.
 */
function quux () {

}

/**
 * @returns Foo bar.
 */
function quux () {

}

/**
 * Foo. {@see Math.sin}.
 */
function quux () {

}

/**
 * Foo {@see Math.sin} bar.
 */
function quux () {

}

/**
 * Foo?
 *
 * Bar!
 *
 * Baz:
 *   1. Foo.
 *   2. Bar.
 */
function quux () {

}

/**
 * Hello:
 * World.
 */
function quux () {

}

/**
 * Hello: world.
 */
function quux () {

}

/**
 *
 */
function quux () {

}

/**
 * @description Foo.
 */
function quux () {

}

/**
 * `foo` is a variable.
 */
function quux () {

}

/**
 * Foo.
 *
 * `foo`.
 */
function quux () {

}

/**
 * @param foo - `bar`.
 */
function quux () {

}

/**
 * @returns {number} `foo`.
 */
function quux () {

}

/**
 * Foo
 * `bar`.
 */
function quux () {

}

/**
 * @example Foo
 */
function quux () {

}

/**
 * @see Foo
 */
function quux () {

}

/**
 * Foo.
 *
 * @param foo Foo.
 */
function quux (foo) {

}

/**
 * Foo.
 *
 * @param foo Foo.
 */
function quux (foo) {

}
// Options: [{"tags":["param"]}]

/**
 * @param foo Foo bar.
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"description":false}}}
// Options: [{"tags":["param"]}]

/**
 *
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"description":false}}}

/**
* We stop loading Items when we have loaded:
*
* 1) The main Item;
* 2) All its variants.
*/

/**
 * This method is working on 2 steps.
 *
 * | Step | Comment     |
 * |------|-------------|
 * |   1  | do it       |
 * |   2  | do it again |
 */

/**
 * This is something that
 * I want to test.
 */
function quux () {

}

/**
 * When making HTTP requests, the
 * URL is super important.
 */
function quux () {

}

/**
 * Sorry, but this isn't a complete sentence, Mr.
 */
function quux () {

}

/**
 * Sorry, but this isn't a complete sentence Mr..
 */
function quux () {

}
// Options: [{"abbreviations":["Mr."]}]

/**
 * Sorry, but this isn't a complete sentence Mr. 
 */
function quux () {

}

/**
 * Sorry, but this isn't a complete sentence Mr. and Mrs..
 */
function quux () {

}
// Options: [{"abbreviations":["Mr","Mrs"]}]

/**
 * This is a complete sentence aMr.
 */
function quux () {

}
// Options: [{"abbreviations":["Mr"]}]

/**
 * This is a complete sentence. But this isn't, Mr.
 */
function quux () {

}

/**
 * This is a complete Mr. Sentence. But this isn't, Mr.
 */
function quux () {

}

/**
 * This is a complete Mr. sentence.
 */
function quux () {

}
// Options: [{"abbreviations":["Mr"]}]

/**
 * This is fun, i.e. enjoyable, but not superlatively so, e.g. not
 * super, wonderful, etc..
 */
function quux () {

}
// Options: [{"abbreviations":["etc","e.g.","i.e."]}]


**
* Do not have dynamic content; e.g. homepage. Here a simple unique id
* suffices.
*/
function quux () {

}
// Options: [{"abbreviations":["etc","e.g.","i.e."]}]
````


<a name="eslint-plugin-jsdoc-rules-require-description"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-description-complete-sentence](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-description-complete-sentence)

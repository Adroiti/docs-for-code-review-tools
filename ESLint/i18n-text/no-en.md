Pattern: Use of English text in string literal

Issue: -

## Description

Reports English text in string literals.

Embedding messages in JavaScript files prevents them from being translated into other languages. An alternative is to embed the translated text in the markup and find it with JavaScript.

This pattern allows the web framework that's generating the markup to use its translation library to insert the appropriate translated text.

Example of **incorrect** code:

```js
el.textContent = "Some message text"
```

Example of **correct** code:

```js
console.log("Informational message")
```

## Further Reading

* [GitHub - i18n-text/no-en](https://github.com/dgraham/eslint-plugin-i18n-text#usage)
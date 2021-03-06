Pattern: Parse error in `<template>`

Issue: -

## Description

This rule tries to parse directives/mustaches in `<template>` by the parser which parses `<script>`. Then reports syntax errors if exist.

<eslint-code-block :rules="{'vue/no-parsing-error': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  {{ . }}
  {{ foo bar }}
  <div :class="*abc*" / @click="def(">
    </span>
  </div id="ghi">
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-parsing-error": ["error", {
    "abrupt-closing-of-empty-comment": true,
    "absence-of-digits-in-numeric-character-reference": true,
    "cdata-in-html-content": true,
    "character-reference-outside-unicode-range": true,
    "control-character-in-input-stream": true,
    "control-character-reference": true,
    "eof-before-tag-name": true,
    "eof-in-cdata": true,
    "eof-in-comment": true,
    "eof-in-tag": true,
    "incorrectly-closed-comment": true,
    "incorrectly-opened-comment": true,
    "invalid-first-character-of-tag-name": true,
    "missing-attribute-value": true,
    "missing-end-tag-name": true,
    "missing-semicolon-after-character-reference": true,
    "missing-whitespace-between-attributes": true,
    "nested-comment": true,
    "noncharacter-character-reference": true,
    "noncharacter-in-input-stream": true,
    "null-character-reference": true,
    "surrogate-character-reference": true,
    "surrogate-in-input-stream": true,
    "unexpected-character-in-attribute-name": true,
    "unexpected-character-in-unquoted-attribute-value": true,
    "unexpected-equals-sign-before-attribute-name": true,
    "unexpected-null-character": true,
    "unexpected-question-mark-instead-of-tag-name": true,
    "unexpected-solidus-in-tag": true,
    "unknown-named-character-reference": true,
    "end-tag-with-attributes": true,
    "duplicate-attribute": true,
    "end-tag-with-trailing-solidus": true,
    "non-void-html-element-start-tag-with-trailing-solidus": false,
    "x-invalid-end-tag": true,
    "x-invalid-namespace": true
  }]
}
```

You can disable HTML syntax errors by options. Please see [WHATWG HTML spec](https://html.spec.whatwg.org/multipage/parsing.html#parse-errors) to know the details of HTML syntax errors. Only `non-void-html-element-start-tag-with-trailing-solidus` is disabled by default because Vue.js supports self-closing tags.

The error codes which have `x-` prefix are original of this rule because errors in tree construction phase have not codified yet.

- `x-invalid-end-tag` enables the errors about the end tags of elements which have not opened.
- `x-invalid-namespace` enables the errors about invalid `xmlns` attributes. See also [step 10. of "create an element for a token"](https://html.spec.whatwg.org/multipage/parsing.html#create-an-element-for-the-token).

## Further Reading

* [eslint-plugin-vue - no-parsing-error](https://eslint.vuejs.org/rules/no-parsing-error.html)

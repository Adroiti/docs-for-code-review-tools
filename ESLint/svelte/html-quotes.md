Pattern: Inconsistent quotes style of HTML attribute

Issue: -

## Description

You can choose quotes of HTML attributes from:

- Double quotes: `<div class="foo">`
- Single quotes: `<div class='foo'>`
- No quotes: `<div class=foo>`

This rule enforces the quotes style of HTML attributes.

```svelte
<script>
  /* eslint svelte/html-quotes: "error" */
</script>

<!-- ✓ GOOD -->
<input type="text" bind:value={text} />
<img {src} alt="{name} dances." />

<!-- ✗ BAD -->
<input type=text bind:value="{text}" />
<img src="{src}" alt='{name} dances.' />
```

## :wrench: Options

```json
{
  "svelte/html-quotes": [
    "error",
    {
      "prefer": "double", // or "single"
      "dynamic": {
        "quoted": false,
        "avoidInvalidUnquotedInHTML": false
      }
    }
  ]
}
```

- `prefer` ... If `"double"`, requires double quotes. If `"single"`, requires single quotes.
- `dynamic` ... Settings for dynamic attribute values and directive values using curly braces.
  - `quoted` ... If `true`, enforce the use of quotes. If `false`, do not allow the use of quotes. The default is `false`.
  - `avoidInvalidUnquotedInHTML` ... If `true`, enforces the use of quotes if they are invalid as HTML attribute when not using quotes. The default is `false`.

## :rocket: Version

This rule was introduced in eslint-plugin-svelte v0.5.0

## :mag: Implementation

- [Rule source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/src/rules/html-quotes.ts)
- [Test source](https://github.com/sveltejs/eslint-plugin-svelte/blob/main/tests/src/rules/html-quotes.ts)

Pattern: Untranslated string in JSX

Issue: -

## Description

Prevents untranslated strings in JSX.

## Why

- It is easy to forget wrapping JSX text in translation functions or components.
- It is easy to forget wrapping certain accessibility attributes (e.g. `aria-label`) in translation functions.

```json
// WORKS
<Button>
  <FormattedMessage defaultMessage="Submit" />
</Button>
// WORKS
<Button>
  {customTranslateFn("Submit")}
</Button>
// WORKS
<input aria-label={intl.formatMessage({defaultMessage: "Label"})} />
// WORKS
<img
  src="/example.png"
  alt={intl.formatMessage({defaultMessage: "Image description"})}
/>
// FAILS
<Button>Submit</Button>
// FAILS
<Button>{'Submit'}</Button>
// FAILS
<Button>{`Te` + 's' + t}</Button>
// FAILS
<input aria-label="Untranslated label" />
// FAILS
<img src="/example.png" alt="Image description" />
// FAILS
<input aria-label={`Untranslated label`} />
```

## Further Reading

* [formatjs - no-multiple-plurals](https://formatjs.io/docs/tooling/linter/#no-literal-string-in-jsx)
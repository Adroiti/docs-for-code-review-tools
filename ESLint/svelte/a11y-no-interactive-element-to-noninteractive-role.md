Pattern: Malformed non-interactive ARIA role

Issue: -

## Description

[WAI-ARIA](https://www.w3.org/TR/wai-aria-1.1/#usage_intro) roles should not be used to convert an interactive element to a non-interactive element. Non-interactive ARIA roles include `article`, `banner`, `complementary`, `img`, `listitem`, `main`, `region` and `tooltip`.

```sv
<!-- A11y: <textarea> cannot have role 'listitem' -->
<textarea role="listitem" />
```

## Further Reading

* [ESLint - a11y-no-interactive-element-to-noninteractive-role](https://svelte.dev/docs#accessibility-warnings-a11y-no-interactive-element-to-noninteractive-role)
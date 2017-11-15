Pattern: Malformed space around `=`

Issue: -

## Description

Requires or bans spaces before and after the `=` token in JSX element attributes. Rule options: `["always", "never"]`.

Example of **incorrect** code (`always`):

```ts
<App someProp="test" />
```

Example of **correct** code (`always`):

```ts
<App someProp = "test" />
```
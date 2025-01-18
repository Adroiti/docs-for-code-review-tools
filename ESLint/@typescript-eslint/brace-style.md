Pattern: Inconsistent brace style

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent brace style for blocks, which can now be configured using the stylistic plugin's brace-style rule.

## Examples

Example of **incorrect** code:
```ts
if (foo)
{
  bar();
}

if (foo) {
  bar();
}
else {
  baz();
}

try
{
  foo();
}
catch(err) {
  bar();
}
```

Example of **correct** code:
```ts
if (foo) {
  bar();
}

if (foo) {
  bar();
} else {
  baz();
}

try {
  foo();
} catch(err) {
  bar();
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.
Pattern: Inconsistent type member delimiter

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent delimiters (semicolons or commas) between interface and type members, which can now be configured using the stylistic plugin's member-delimiter-style rule.

## Examples

Example of **incorrect** code:
```ts
// Mixed delimiters
interface Person {
  name: string,
  age: number;
  location: string,
}

// Missing delimiters
type Animal = {
  species: string
  breed: string
}

// Wrong delimiter style
interface Config {
  api: string;
  timeout: number;  // trailing semicolon
}
```

Example of **correct** code:
```ts
// Consistent semicolons
interface Person {
  name: string;
  age: number;
  location: string;
}

// Consistent commas
type Animal = {
  species: string,
  breed: string,
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.
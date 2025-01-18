Pattern: Inconsistent spacing around keywords

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing around keywords like `if`, `for`, `function`, etc., which can now be configured using the stylistic plugin's keyword-spacing rule.

## Examples

Example of **incorrect** code:
```ts
if(foo) {}
function foo (){}
return[1, 2, 3];
try{
  something();
}catch(e){}
typeof!foo;
```

Example of **correct** code:
```ts
if (foo) {}
function foo() {}
return [1, 2, 3];
try {
  something();
} catch (e) {}
typeof !foo;
```

See [eslint.style](https://eslint.style) for the current version of this rule.
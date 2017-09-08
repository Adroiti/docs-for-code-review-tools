Pattern: Type assertion on object literal

Issue: -

## Description

Forbids an object literal to appear in a type assertion expression. Casting to `any` is still allowed.  
  
Rationale: Always prefer `const x: T = { ... };` to `const x = { ... } as T;`. The type assertion in the latter case is either unnecessary or hides an error. The compiler will warn for excess properties with this syntax, but not missing required fields. For example: `const x: { foo: number } = {}` will fail to compile, but `const x = {} as { foo: number }` will succeed.

## Further Reading

* [TSLint - no-object-literal-type-assertion](https://palantir.github.io/tslint/rules/no-object-literal-type-assertion)
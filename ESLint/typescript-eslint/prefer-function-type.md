# Enforce using function types instead of interfaces with call signatures.

This rule suggests using a function type instead of an interface or object type literal with a single call signature.

## Examples

Examples of **incorrect** code for this rule:

```ts
interface Example {
  (): string;
}
```

Examples of **correct** code for this rule:

```ts
type Example = () => string;
```

## When Not To Use It

If you specifically want to use an interface or type literal with a single call signature for stylistic reasons, you can avoid this rule.
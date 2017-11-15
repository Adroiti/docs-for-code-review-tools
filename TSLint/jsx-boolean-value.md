Pattern: Malformed boolean value

Issue: -

## Description

When using a boolean attribute in JSX, you can set the attribute value to true or omit the value. This rule will enforce one or the other to keep consistency in your code. Default is set to `always`.

Example of **incorrect** code (`always`):

```ts
function render(){
  return(
    <Tag readOnly />
         ~~~~~~~~ [Value must be set for boolean attributes]
  );
}
```

Example of **correct** code (`always`):

```ts
function render(){
  return(
    <Tag readOnly={true} />
  );
}
```
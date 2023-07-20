Pattern: Component not working with Fast Refresh

Issue: -

## Description

Validate that your components can safely be updated with fast refresh.

Example of **incorrect** code:

```jsx
export const foo = () => {};
export const Bar = () => <></>;

export default function () {}
export default compose()(MainComponent)
```
Example of **correct** code:

```jsx
export default function Foo() {
  return <></>;
}

const foo = () => {};
export const Bar = () => <></>;
```

## Further Reading

* [eslint-plugin-react-refresh](https://github.com/ArnaudBarre/eslint-plugin-react-refresh#usage)
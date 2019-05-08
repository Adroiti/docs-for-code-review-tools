Pattern: Used JSX variable

Issue: -

## Description

This rule will find variables used in JSX and mark them as used. It has an effect when the `no-unused-vars` rule is enabled. Without this rule this code triggers warning:

```jsx
import HelloWorld from './HelloWorld';

export default {
  render () {
    return (
      <HelloWorld msg="world"/>
    )
  },
};
```

After turning on, `Hello` is being marked as used and `no-unused-vars` rule doesn't report an issue.

If you are not using JSX or if you do not use the `no-unused-vars` rule then you can disable this rule.

## Further Reading

* [eslint-plugin-vue - jsx-uses-vars](https://eslint.vuejs.org/rules/jsx-uses-vars.html)

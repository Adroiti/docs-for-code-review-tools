Pattern: jsx uses vars

Issue: -

## Description

Without this rule this code triggers warning:

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

## :mute: When Not To Use It

If you are not using JSX or if you do not use the `no-unused-vars` rule then you can disable this rule.

## Further Reading

* [eslint-plugin-vue - jsx-uses-vars](https://eslint.vuejs.org/rules/jsx-uses-vars.html)

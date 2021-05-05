Pattern: Use of vanilla emotion

Issue: -

## Description

This rule reports an error if there is an import from the `emotion` package which is not recommended if you are using emotion with React.

Examples of **incorrect** code for this rule.

```jsx
import { css } from '@emotion/css'
```

## When Not To Use It

If you are using vanilla emotion because you are not using React.

## Further Reading

* [GitHub - no-vanilla](https://github.com/emotion-js/emotion/blob/main/packages/eslint-plugin/docs/rules/no-vanilla.md)
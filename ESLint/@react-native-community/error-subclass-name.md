Pattern: Invalid error class name

Issue: -

## Description

This rule is primarily used for developing React Native itself and is not generally applicable to other projects.

Enforces that error classes ( = classes with PascalCase names ending with Error) only extend other error classes, and that regular functions don't have names that could be mistaken for those of error classes.

## Further Reading

* [GitHub - error-subclass-name](https://github.com/facebook/react-native/blob/master/packages/eslint-plugin-react-native-community/error-subclass-name.js)
Pattern: Unneeded property in React Props/State

Issue: -

## Description

Remove unneeded properties defined in React Props and State interfaces.
Any interface named Props or State is defined as a React interface. All
fields in these interfaces must be referenced. This rule can be
configured with Regexes to match custom Props and State interface names.

## Configuration

Example for including all interfaces ending with Props or State:
```
[true, {
    'props-interface-regex': 'Props$',
    'state-interface-regex': 'State$'
}]
```

## Further Reading

* [TSLint - react-unused-props-and-state](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
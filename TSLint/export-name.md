Pattern: Mismatched export name

Issue: -

## Description

The name of the exported module must match the filename of the source
file. This is case-insensitive by default but ignores file extension.

## Configuration

It can be configured to be case-insensitive or to allow names matching a regex. For example, to allow names that differ only in case and an exported name like myChartOptions, then configure the rule like this:
```
"export-name": [true, {
    "ignore-case": true,
    "allow": ["myChartOptions"]
}]
```

You can also just give a list of allowed names:
```
"export-name": [true, "myChartOptions"]
```

## Further Reading

* [TSLint - export-name](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
Pattern: Missing locale for `DateFormat`

Issue: -

## Description

Be sure to specify a `Locale` when creating a new instance of `SimpleDateFormat`; the class is locale-sensitive. If you instantiate `SimpleDateFormat` without a `Locale` parameter, it will format the date and time according to the default `Locale`. Both the pattern and the `Locale` determine the format. For the same pattern, `SimpleDateFormat` may format a date and time differently if the Locale varies.

``` groovy
// violation, missing locale
new SimpleDateFormat('pattern')

// OK, includes locale
new SimpleDateFormat('pattern', Locale.US)

// OK, includes a variable that perhaps is a locale
new SimpleDateFormat('pattern', locale)
```

## Further Reading

* [CodeNarc - SimpleDateFormatMissingLocale](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#simpledateformatmissinglocale-rule)
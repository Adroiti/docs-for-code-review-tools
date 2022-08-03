Pattern: Implicit default locale

Issue: -

## Description

Prefer passing `java.util.Locale` explicitly than using implicit default value when formatting strings. The default locale is almost always not appropriate for machine-readable text like HTTP headers. For example if locale with tag `ar-SA-u-nu-arab` is a current default then `%d` placeholders will be evaluated to numbers consisting of Eastern-Arabic (non-ASCII) digits. `java.util.Locale.US` is recommended for machine-readable output.

Example of **incorrect** code:

```kotlinString.format("Timestamp: %d", System.currentTimeMillis())```

Example of **correct** code:

```kotlinString.format(Locale.US, "Timestamp: %d", System.currentTimeMillis())```

## Further Reading

* [Detekt - ImplicitDefaultLocale](https://detekt.dev/docs/rules/potential-bugs/#implicitdefaultlocale)
Pattern: Use of blacklisted element

Issue: -

## Description

Blacklists usage of specific elements in ICU message.

```json
enum Element {
  // literal text, like `defaultMessage: 'some text'`
  literal = 'literal',
  // placeholder, like `defaultMessage: '{placeholder} var'`
  argument = 'argument',
  // number, like `defaultMessage: '{placeholder, number} var'`
  number = 'number',
  // date, like `defaultMessage: '{placeholder, date} var'`
  date = 'date',
  // time, like `defaultMessage: '{placeholder, time} var'`
  time = 'time',
  // select, like `defaultMessage: '{var, select, foo{one} bar{two}} var'`
  select = 'select',
  // selectordinal, like `defaultMessage: '{var, selectordinal, one{one} other{two}} var'`
  selectordinal = 'selectordinal',
  // plural, like `defaultMessage: '{var, plural, one{one} other{two}} var'`
  plural = 'plural',
}
```


## Further Reading

* [formatjs - blacklist-elements](https://formatjs.io/docs/tooling/linter/#blacklist-elements)
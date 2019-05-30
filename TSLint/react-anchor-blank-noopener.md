Pattern: Missing `rel="noreferrer"` for blank anchor tag

Issue: -

## Description

For security reasons, anchor tags with `target="_blank"` should also include `rel="noreferrer"`. 

In order to restrict the behavior `window.opener` access, the original page needs to add a
`rel="noopener"` attribute to any link that has `target="_blank"`.
However, Firefox does not support that tag, so you should actually use
`rel="noopener noreferrer"` for full coverage.  
By default, the rule considers the use of `rel="noreferrer"` as
sufficient. The option `'force-rel-redundancy'` can be passed to require
`rel="noopener noreferrer"`.

## Further Reading

* [TSLint - react-anchor-blank-noopener](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
* [The target="_blank" vulnerability by example](https://dev.to/ben/the-targetblank-vulnerability-by-example)
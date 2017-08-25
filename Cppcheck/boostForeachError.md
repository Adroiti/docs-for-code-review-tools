Pattern: `BOOST_FOREACH` caches `end()` iterator

Issue: -

## Description

`BOOST_FOREACH` caches the `end()` iterator. It’s undefined behavior if you modify the container inside.

## Further Reading

* [Common Weakness Enumeration (CWE) - 664](https://cwe.mitre.org/data/definitions/664.html)
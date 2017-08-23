Pattern: Stl if str find

Issue: -

## Description

Either inefficient or wrong usage of string::`find()`. string::`compare()` will be faster if string::find’s result is compared with 0, because it will not scan the whole string. If your intention is to check that there are no findings in the string, you should compare with std::string::npos.

## Further Reading

* [Common Weakness Enumeration (CWE) - 597](https://cwe.mitre.org/data/definitions/597.html)
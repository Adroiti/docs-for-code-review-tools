Pattern: Operator eq

Issue: -

## Description

The class::operator= does not conform to standard C/C++ behaviour. To conform to standard C/C++ behaviour, return a reference to self (such as: `class &class::operator=(..) { .. return *this; }`. For safety reasons it might be better to not fix this message. If you think that safety is always more important than conformance then please ignore/suppress this message. For more details about this topic, see the book "Effective C++" by Scott Meyers.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)
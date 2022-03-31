Pattern: Use of non-ASCII file name

Issue: -

## Description

Some editors don't support non-ASCII file names properly. Even though Python supports UTF-8 files since Python 3.5 this isn't recommended for interoperability.

## Further Reading

* [PEP 489 - Export Hook Name](https://www.python.org/dev/peps/pep-0489/#export-hook-name)
* [PEP 672 - Confusable Characters in Identifiers](https://www.python.org/dev/peps/pep-0672/#confusable-characters-in-identifiers)
Pattern: Use of tab character

Issue: -

## Description

Checks that there are no tab characters (`'\t'`) in the source code. 

Rationale: 

  - Developers should not need to configure the tab width of their text editors in order to be able to read source code. 
  - In a distributed development environment where diffs are sent to the mailing lists by both developers and the version control system (which sends commit log messages), the use tabs makes it impossible to preserve legibility.

## Further Reading

* [CoffeeLint - no_tabs](https://coffeelint.github.io/#options)
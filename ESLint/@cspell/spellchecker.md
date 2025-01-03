Pattern: Spelling error

Issue: -

## Description

Checks spelling in source code files and comments to ensure correct spelling. Uses CSpell dictionary for spell checking and supports custom dictionaries and word lists.

## Examples

```javascript
// ✗ BAD
const mesage = 'Hello world'; // Misspelled "message"

// ✓ GOOD
const message = 'Hello world';

/**
 * You can also use inline comments to ignore specific terms:
 * cspell:ignore specifictechnicalterm
 * Or disable for a block:
 * cspell:disable
 * cspell:enable
 */
```
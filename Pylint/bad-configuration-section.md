Pattern: Malformed TOML configuration section

Issue: -

## Description

Emitted for misplaced option in Pylint's top level namespace for TOML configuration. Top-level dictionaries or option defined in the wrong section will still silently not be taken into account, which is tracked in a follow-up issue.
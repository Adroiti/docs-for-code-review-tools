Pattern: Missing use of `from` import

Issue: -

## Description

Emitted when a submodule/member of a package is imported and aliased with the same name. E.g., instead of `import pandas.DataFrame as DataFrame` use `from pandas import DataFrame`.

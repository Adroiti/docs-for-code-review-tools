Pattern: Keyword argument before variable positional argument

Issue: -

## Description

This rule is emitted when a function is defined with a keyword argument appearing before variable-length positional arguments (`*args`). 

This may lead to args list getting modified if keyword argument's value is not provided in the function call assuming it will take default value provided in the definition.
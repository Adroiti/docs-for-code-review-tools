Pattern: AWS provider has access credentials specified

Issue: -

## Description

The AWS provider block should not contain hardcoded credentials. These can be passed in securely as runtime using environment variables.

**Resolution**: Don't include access credentials in plain text.

## Examples

Example of **incorrect** code:

```terraform
provider "aws" {
  access_key = "AKIAABCD12ABCDEF1ABC"
  secret_key = "s8d7ghas9dghd9ophgs9"
}
```

Example of **correct** code:

```terraform
provider "aws" {
}
```
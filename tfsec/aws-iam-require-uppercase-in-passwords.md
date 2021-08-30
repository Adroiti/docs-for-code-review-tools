Pattern: IAM Password policy should have requirement for at least one uppercase character

Issue: -

## Description

IAM account password policies should ensure that passwords content including at least one uppercase character.

**Resolution**: import (.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# require_uppercase_characters not set
	# ...
}
```

Example of **correct** code:

```terraform
resource "aws_iam_account_password_policy" "good_example" {
	# ...
	require_uppercase_characters = true
	# ...
}
```
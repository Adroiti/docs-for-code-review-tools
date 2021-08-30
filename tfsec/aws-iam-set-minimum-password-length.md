Pattern: IAM Password policy should have minimum password length of 14 or more characters

Issue: -

## Description

IAM account password policies should ensure that passwords have a minimum length. 

The account password policy should be set to enforce minimum password length of at least 14 characters.

**Resolution**: import (.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# minimum_password_length not set
	# ...
}
```

Example of **correct** code:

```terraform
resource "aws_iam_account_password_policy" "good_example" {
	# ...
	minimum_password_length = 14
	# ...
}
```
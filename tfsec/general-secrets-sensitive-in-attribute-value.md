Pattern: Attribute has potentially sensitive data

Issue: -

## Description

Sensitive data stored in attributes can result in compromised data. Sensitive data should be passed in through secret variables

**Resolution**: Check the code for vulnerabilities and move to variables.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_instance" "bad_example" {
	instance_type = "t2.small"

	user_data = <<EOF
		Password = "something secret"
EOF

}
```

Example of **correct** code:

```terraform
variable "password" {
	type = string
}

resource "aws_instance" "good_instance" {
	instance_type = "t2.small"

	user_data = <<EOF
		export EDITOR=vimacs
EOF

}
```
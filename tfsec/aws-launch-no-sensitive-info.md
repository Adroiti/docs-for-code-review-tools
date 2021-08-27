Pattern: Use of possibly sensitive data in Launch configuration EBS

Issue: -

## Description

When creating Launch Configurations, user data can be used for the initial configuration of the instance. User data must not contain any sensitive data.

**Resolution**: Don't use sensitive data in user data.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_launch_configuration" "as_conf" {
  name          = "web_config"
  image_id      = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
  user_data     = <<EOF
export DATABASE_PASSWORD=\"SomeSortOfPassword\"
EOF
}
```

Example of **correct** code:

```terraform
resource "aws_launch_configuration" "as_conf" {
  name          = "web_config"
  image_id      = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
  user_data     = <<EOF
export GREETING="Hello there"
EOF
}
```
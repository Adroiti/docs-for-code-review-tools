Pattern: Use of sensitive data in AWS EC2 instance

Issue: -

## Description

EC2 instance data is used to pass start up information into the EC2 instance. This user-data must not contain access key credentials. Instead use an IAM Instance Profile assigned to the instance to grant access to other AWS Services.

**Resolution**: Remove sensitive data from the EC2 instance user-data.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_instance" "bad_example" {

  ami           = "ami-12345667"
  instance_type = "t2.small"

  user_data = <<EOF
export AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
export AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
export AWS_DEFAULT_REGION=us-west-2 
EOF
}
```

Example of **correct** code:

```terraform
resource "aws_iam_instance_profile" "good_example" {
    // ...
}

resource "aws_instance" "good_example" {
  ami           = "ami-12345667"
  instance_type = "t2.small"

  iam_instance_profile = aws_iam_instance_profile.good_profile.arn

  user_data = <<EOF
  export GREETING=hello
EOF
}
```
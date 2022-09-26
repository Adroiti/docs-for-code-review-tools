Pattern: Disabled HTTP token requirement for AWS IMDS

Issue: -

## Description

IMDS v2 (Instance Metadata Service) introduced session authentication tokens which improve security when talking to IMDS.
By default `aws_instance` resource sets IMDS session auth tokens to be optional. 
To fully protect IMDS you need to enable session tokens by using `metadata_options` block and its `http_tokens` variable set to `required`.

**Resolution**: Enable HTTP token requirement for IMDS.

## Examples

The following example will fail the aws-ec2-enforce-launch-config-http-token-imds check.

```terraform

 resource "aws_launch_template" "bad_example" {
	 image_id      = "ami-005e54dee72cc1d00"
	 instance_type = "t2.micro"
 }
 
```

The following example will pass the aws-ec2-enforce-launch-config-http-token-imds check.
```terraform

 resource "aws_launch_template" "good_example" {
	 image_id      = "ami-005e54dee72cc1d00"
	 instance_type = "t2.micro"
	 metadata_options {
	   http_tokens = "required"
	 }	
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance#metadata-options](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance#metadata-options)
- [https://aws.amazon.com/blogs/security/defense-in-depth-open-firewalls-reverse-proxies-ssrf-vulnerabilities-ec2-instance-metadata-service](https://aws.amazon.com/blogs/security/defense-in-depth-open-firewalls-reverse-proxies-ssrf-vulnerabilities-ec2-instance-metadata-service)
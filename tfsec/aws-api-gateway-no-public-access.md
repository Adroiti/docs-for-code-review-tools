Pattern: No public access to API Gateway methods

Issue: -

## Description

API Gateway methods should be protected by authorization or api key. OPTION verb calls can be used without authorization

**Resolution**: Use and authorization method or require API Key.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_api_gateway_method" "bad_example" {
  rest_api_id   = aws_api_gateway_rest_api.MyDemoAPI.id
  resource_id   = aws_api_gateway_resource.MyDemoResource.id
  http_method   = "GET"
  authorization = "NONE"
}
```

Example of **correct** code:

```terraform
resource "aws_api_gateway_method" "good_example" {
  rest_api_id   = aws_api_gateway_rest_api.MyDemoAPI.id
  resource_id   = aws_api_gateway_resource.MyDemoResource.id
  http_method   = "GET"
  authorization = "AWS_IAM"
}
```
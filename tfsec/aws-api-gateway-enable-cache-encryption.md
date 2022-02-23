Pattern: Disabled cache encryption for AWS API Gateway

Issue: -

## Description

Method cache encryption ensures that any sensitive data in the cache is not vulnerable to compromise in the event of interception

**Resolution**: Enable cache encryption.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_api_gateway_method_settings" "bad_example" {
  rest_api_id = aws_api_gateway_rest_api.example.id
  stage_name  = aws_api_gateway_stage.example.stage_name
  method_path = "path1/GET"

  settings {
    metrics_enabled = true
    logging_level   = "INFO"
    cache_data_encrypted = false
  }
}
```

Example of **correct** code:

```terraform
resource "aws_api_gateway_method_settings" "good_example" {
  rest_api_id = aws_api_gateway_rest_api.example.id
  stage_name  = aws_api_gateway_stage.example.stage_name
  method_path = "path1/GET"

  settings {
    metrics_enabled = true
    logging_level   = "INFO"
    cache_data_encrypted = true
  }
}
```
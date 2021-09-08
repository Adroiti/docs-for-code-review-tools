Pattern: API Gateway must have X-Ray tracing enabled

Issue: -

## Description

X-Ray tracing enables end-to-end debugging and analysis of all API Gateway HTTP requests.

**Resolution**: Enable tracing.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_api_gateway_stage" "bad_example" {
  stage_name    = "prod"
  rest_api_id   = aws_api_gateway_rest_api.test.id
  deployment_id = aws_api_gateway_deployment.test.id
  xray_tracing_enabled = false
}
```

Example of **correct** code:

```terraform
resource "aws_api_gateway_stage" "good_example" {
  stage_name    = "prod"
  rest_api_id   = aws_api_gateway_rest_api.test.id
  deployment_id = aws_api_gateway_deployment.test.id
  xray_tracing_enabled = true
}
```
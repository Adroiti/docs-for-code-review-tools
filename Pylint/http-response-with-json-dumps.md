Pattern: Use of `HttpResponse(json.dumps(data))`

Issue: -

## Description

Used when `json.dumps()` is used as an argument to `HttpResponse()`. Use `JsonResponse(data)` instead.
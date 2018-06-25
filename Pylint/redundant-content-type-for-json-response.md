Pattern: Redundant `content_type` parameter for `JsonResponse()`

Issue: -

## Description

Used when `JsonResponse()` contains `content_type` parameter. This is either redundant or the `content_type` is not JSON which is probably an error.
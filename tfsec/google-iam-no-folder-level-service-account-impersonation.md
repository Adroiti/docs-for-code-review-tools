Pattern: Use of folder-level service account access for Google IAM

Issue: -

## Description

Users with service account access at folder level can impersonate any service account. Instead, they should be given access to particular service accounts as required.

**Resolution**: Provide access at the service-level instead of folder-level, if required.

## Examples

Example of **incorrect** code:

```terraform

```

Example of **correct** code:

```terraform
resource "google_folder_iam_binding" "folder-123" {
	folder = "folder-123"
	role    = "roles/nothingInParticular"
}
```
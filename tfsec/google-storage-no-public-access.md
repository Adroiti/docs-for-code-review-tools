Pattern: Enabled public access for Google Cloud Storage bucket

Issue: -

## Description

Using `allUsers` or `allAuthenticatedUsers` as members in an IAM member/binding causes data to be exposed outside of the organisation.

**Resolution**: Restrict public access to the bucket.

## Examples

Example of **incorrect** code:

```terraform
resource "google_storage_bucket_iam_binding" "binding" {
	bucket = google_storage_bucket.default.name
	role = "roles/storage.admin"
	members = [
		"allAuthenticatedUsers",
	]
}
```

Example of **correct** code:

```terraform
resource "google_storage_bucket_iam_binding" "binding" {
	bucket = google_storage_bucket.default.name
	role = "roles/storage.admin"
	members = [
		"user:jane@example.com",
	]
}
```
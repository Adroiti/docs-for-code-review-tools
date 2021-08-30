Pattern: IAM granted directly to user

Issue: -

## Description

Permissions should not be directly granted to users, you identify roles that contain the appropriate permissions, and then grant those roles to the user. 

Granting permissions to users quickly become unwieldy and complex to make large scale changes to remove access to a particular resource.

Permissions should be granted on roles, groups, services accounts instead.

**Resolution**: Roles should be granted permissions and assigned to users.

## Examples

Example of **incorrect** code:

```terraform
resource "google_project_iam_binding" "bad_example" {
	members = [
		"user:test@example.com",
		]
}

resource "google_project_iam_member" "bad_example" {
	member = "user:test@example.com"
}
```

Example of **correct** code:

```terraform
resource "google_project_iam_binding" "good_example" {
	members = [
		"group:test@example.com",
		]
}

resource "google_storage_bucket_iam_member" "good_example" {
	member = "serviceAccount:test@example.com"
}
```
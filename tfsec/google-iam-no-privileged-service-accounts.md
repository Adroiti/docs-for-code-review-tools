Pattern: Privileged service account for Google IAM

Issue: -

## Description

Service accounts should have a minimal set of permissions assigned in order to do their job. They should never have excessive access as if compromised, an attacker can escalate privileges and take over the entire account.

**Resolution**: Limit service account access to minimal required set.

## Examples

Example of **incorrect** code:

```terraform
resource "google_service_account" "test" {
  account_id   = "account123"
  display_name = "account123"
}

resource "google_project_iam_member" "project" {
	project = "your-project-id"
	role    = "roles/owner"
	member  = "serviceAccount:${google_service_account.test.email}"
}
```

Example of **correct** code:

```terraform
resource "google_service_account" "test" {
	account_id   = "account123"
	display_name = "account123"
}

resource "google_project_iam_member" "project" {
	project = "your-project-id"
	role    = "roles/logging.logWriter"
	member  = "serviceAccount:${google_service_account.test.email}"
}
```
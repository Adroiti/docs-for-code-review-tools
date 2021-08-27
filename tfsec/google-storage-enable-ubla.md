Pattern: Disabled uniform bucket-level access for Cloud Storage bucket

Issue: -

## Description

When you enable uniform bucket-level access on a bucket, Access Control Lists (ACLs) are disabled, and only bucket-level Identity and Access Management (IAM) permissions grant access to that bucket and the objects it contains. You revoke all access granted by object ACLs and the ability to administrate permissions using bucket ACLs.

**Resolution**: Enable uniform bucket level access to provide a uniform permissioning system.

## Examples

Example of **incorrect** code:

```terraform
resource "google_storage_bucket" "static-site" {
	name          = "image-store.com"
	location      = "EU"
	force_destroy = true
	
	uniform_bucket_level_access = false
	
	website {
		main_page_suffix = "index.html"
		not_found_page   = "404.html"
	}
	cors {
		origin          = ["http://image-store.com"]
		method          = ["GET", "HEAD", "PUT", "POST", "DELETE"]
		response_header = ["*"]
		max_age_seconds = 3600
	}
}
```

Example of **correct** code:

```terraform
resource "google_storage_bucket" "static-site" {
	name          = "image-store.com"
	location      = "EU"
	force_destroy = true
	
	uniform_bucket_level_access = true
	
	website {
		main_page_suffix = "index.html"
		not_found_page   = "404.html"
	}
	cors {
		origin          = ["http://image-store.com"]
		method          = ["GET", "HEAD", "PUT", "POST", "DELETE"]
		response_header = ["*"]
		max_age_seconds = 3600
	}
}
```
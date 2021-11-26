Pattern: Disabled signed commits requirement

Issue: -

## Description

You cannot guarantee the source of unsigned commits. Set `require_signed_commits` attribute to `true` to enable this setting.

**Resolution**: require signed commits for all protected branches.

## Examples

Example of **incorrect** code:

```terraform
resource "github_branch_protection" "bad_example" {
  repository_id = github_repository.example.node_id
  
  pattern          = "main"
  enforce_admins   = true
  allows_deletions = true
  require_signed_commits = false
}
```

Example of **correct** code:

```terraform
resource "github_branch_protection" "good_example" {
  repository_id = github_repository.example.node_id
  pattern          = "main"
  enforce_admins   = true
  allows_deletions = true
  require_signed_commits = true
}
```
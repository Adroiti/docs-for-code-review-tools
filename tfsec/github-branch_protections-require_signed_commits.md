Pattern: Missing signed commits for GitHub branch protection

Issue: -

## Description

GitHub branch protection should be set to require signed commits.

You can do this by setting the `require_signed_commits` attribute to 'true'.

**Resolution**: Require signed commits.

## Examples

The following example will fail the github-branch_protections-require_signed_commits check.
```terraform

 resource "github_branch_protection" "good_example" {
   repository_id = "example"
   pattern       = "main"

   require_signed_commits = false
 }
 
```

The following example will pass the github-branch_protections-require_signed_commits check.
```terraform

 resource "github_branch_protection" "good_example" {
   repository_id = "example"
   pattern       = "main"

   require_signed_commits = true
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/integrations/github/latest/docs/resources/branch_protection](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/branch_protection)
- [https://registry.terraform.io/providers/integrations/github/latest/docs/resources/branch_protection#require_signed_commits](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/branch_protection#require_signed_commits)
- [https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)
- [https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches#require-signed-commits](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches#require-signed-commits)
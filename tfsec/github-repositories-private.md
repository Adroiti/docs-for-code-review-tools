Pattern: Use of public GitHub repository

Issue: -

## Description

Github repository should be set to be private.

You can do this by either setting `private` attribute to 'true' or `visibility` attribute to 'internal' or 'private'.

**Resolution**: Make sensitive or commercially important repositories private.

## Examples

Example of **incorrect** code:

```terraform
resource "github_repository" "bad_example" {
  name        = "example"
  description = "My awesome codebase"

  visibility  = "public"

  template {
    owner = "github"
    repository = "terraform-module-template"
  }
}
```

Example of **correct** code:

```terraform
resource "github_repository" "good_example" {
  name        = "example"
  description = "My awesome codebase"

  visibility  = "private"

  template {
    owner = "github"
    repository = "terraform-module-template"
  }
}
```
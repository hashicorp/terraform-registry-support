# Terraform Registry Support

This repository is for reporting bugs and issues with the Terraform Registry [registry.terraform.io](https://registry.terraform.io/).

Use this tracker for problems with the Registry website itself, including issues with browsing, discovery, display, indexing, publishing visibility, and other Registry behavior.

## Use this repository for

Please open an issue here for problems such as:

- Broken pages or unexpected Registry behavior
- Search or indexing issues
- Providers or modules not appearing as expected in the Registry
- Incorrect metadata, versions, or display in Registry pages
- Problems with publisher, namespace, or module/provider pages
- Reproducible UI, rendering, or navigation issues
- Documentation or content problems on Registry pages, if applicable

## Please do not use this repository for

This repository is **not** the right place for:

- Terraform CLI bugs or feature requests
- Bugs in a specific provider implementation
- Bugs in a specific module implementation
- Feature requests for individual providers or modules
- General usage questions or troubleshooting for Terraform configuration

If your issue is not with the Terraform Registry itself, please file it in the appropriate repository or support channel.

## Where to report other issues

Depending on the problem, one of these may be a better fit:

- **Terraform CLI issues:** [hashicorp/terraform](https://github.com/hashicorp/terraform)
- **Provider-specific issues:** the relevant provider repository
- **Module-specific issues:** the module's source repository
- **Sensitive security reports:** please follow HashiCorp's security disclosure process rather than opening a public issue

## Before opening an issue

Before filing, please take a quick look to see if:

- An existing issue already describes the same problem
- The issue is reproducible
- The problem is with the Registry itself, rather than Terraform CLI, a provider, or a module implementation

## What to include in an issue

To help us triage and investigate, please include as much of the following as you can:

- The full Registry URL where the issue occurs
- A short summary of the problem
- Clear steps to reproduce
- The expected behavior
- The actual behavior
- Screenshots, screen recordings, or error messages
- Browser and version
- Operating system
- Approximate date/time when you observed the issue
- Any additional context that may help reproduce or diagnose the problem

## Good issue examples

Helpful reports usually answer questions like:

- What page or Registry artifact is affected?
- What exactly did you do?
- What did you expect to happen?
- What happened instead?
- Does it happen consistently?

## Response expectations

Issues in this repository are intended to help the Terraform team track and triage problems with the Registry. While we may not be able to respond to every report immediately, clear and reproducible issues are the easiest to investigate and route appropriately.

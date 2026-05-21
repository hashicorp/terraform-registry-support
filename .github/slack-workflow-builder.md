# Slack Workflow Builder Setup

Create a Slack workflow named `Terraform Registry Issue Notifications` in the `ibm-hashicorp` workspace.

## Trigger

Use a `Webhook` trigger.

Copy the generated webhook URL into the GitHub repository secret:

- `SLACK_TERRAFORM_REGISTRY_SUPPORT_WORKFLOW_WEBHOOK_URL`

## Variables

The GitHub Action sends these fields in the webhook payload:

- `issue_type`
- `repository`
- `issue_title`
- `issue_url`
- `issue_number`
- `issue_author`
- `issue_labels`
- `request_type`
- `issue_summary`
- `registry_url`
- `bug_description`
- `expected_behavior`
- `reproduction`
- `artifact_url`
- `requestor_github`
- `new_owner_github`
- `requested_action`
- `reason`
- `current_repo`
- `new_repo`
- `current_verification`
- `new_verification`

## Branching

Add a branch step on `issue_type` with these cases:

- `bug`
- `ownership`
- `removal`
- `source-repo-change`
- `artifact-management`
- default

## Messages

Send each message to `#support-terraform-registry`.

### bug

```text
:beetle: *New Registry bug report*
*Issue:* <{{issue_url}}|#{{issue_number}} {{issue_title}}>
*Opened by:* `{{issue_author}}`
*Repo:* `{{repository}}`
*Labels:* `{{issue_labels}}`

*Registry URL:* {{registry_url}}
*Bug:* {{bug_description}}
*Expected:* {{expected_behavior}}
*Repro:* {{reproduction}}
```

### ownership

```text
:key: *New artifact ownership request*
*Issue:* <{{issue_url}}|#{{issue_number}} {{issue_title}}>
*Opened by:* `{{issue_author}}`
*Repo:* `{{repository}}`

*Artifact:* {{artifact_url}}
*Requestor:* {{requestor_github}}
*New owner:* {{new_owner_github}}
*Action:* {{requested_action}}
*Reason:* {{reason}}
*Verification:* {{current_verification}}
```

### removal

```text
:warning: *New artifact removal request*
*Issue:* <{{issue_url}}|#{{issue_number}} {{issue_title}}>
*Opened by:* `{{issue_author}}`
*Repo:* `{{repository}}`

*Artifact:* {{artifact_url}}
*Requestor:* {{requestor_github}}
*Action:* {{requested_action}}
*Reason:* {{reason}}
*Verification:* {{current_verification}}
```

### source-repo-change

```text
:twisted_rightwards_arrows: *New provider source repository change request*
*Issue:* <{{issue_url}}|#{{issue_number}} {{issue_title}}>
*Opened by:* `{{issue_author}}`
*Repo:* `{{repository}}`

*Artifact:* {{artifact_url}}
*Requestor:* {{requestor_github}}
*Current repo:* {{current_repo}}
*Requested repo:* {{new_repo}}
*Action:* {{requested_action}}
*Verification:* current={{current_verification}}, new={{new_verification}}
```

### artifact-management

```text
:package: *New artifact management request*
*Issue:* <{{issue_url}}|#{{issue_number}} {{issue_title}}>
*Opened by:* `{{issue_author}}`
*Repo:* `{{repository}}`

*Request type:* {{request_type}}
*Artifact:* {{artifact_url}}
*Requestor:* {{requestor_github}}
*Action:* {{requested_action}}
*Reason:* {{reason}}
*Verification:* current={{current_verification}}, new={{new_verification}}
```

### default

```text
:github: *New Terraform Registry support issue*
*Issue:* <{{issue_url}}|#{{issue_number}} {{issue_title}}>
*Opened by:* `{{issue_author}}`
*Repo:* `{{repository}}`
*Labels:* `{{issue_labels}}`

{{issue_summary}}
```

## Notes

- Insert Slack variables using Workflow Builder's variable picker rather than typing the braces manually if Slack rewrites the formatting.
- The GitHub Action is implemented in `.github/workflows/notify-slack-on-issue.yml`.

---
name: Public registry artifact management
about: Request ownership changes, removal from the registry, or provider source repository updates for a public registry artifact
title: "[Artifact Management]: "
labels: ""
assignees: ""
---

## Request type

Please select the type of request by replacing `[ ]` with `[x]`:

- [ ] Change artifact ownership
- [ ] Remove artifact from registry
- [ ] Change provider source repository

## Registry artifact details

- Registry link:
- Artifact type: [ ] Provider [ ] Module [ ] Other
- Current source repository URL:
- Requested new source repository URL (if applicable):

## Request details

Please describe the requested change clearly and concisely.

- Requested action:
- Reason for request:

## Requestor details

- Requestor name:
- Requestor email:
- GitHub username:
- New owner GitHub username (for ownership changes only):

## Ownership verification requirements

To protect registry users and publishers, we can only perform administrative changes after verifying ownership of the published artifact.

### For ownership changes or removal from the registry

Please create a file named `.terraform-registry` in the root of the artifact repository on the **default branch** with the following contents:

Request: <concisely explain your request, e.g. "change owner to user123" or "remove from registry">
Registry Link: <link to your artifact on the Registry>
Request by: <the email associated with this request>

### For provider source repository changes

Please create a file named `.terraform-registry` in the root of **both** the current repository and the new repository on the **default branch** with the following contents:

Request: <concisely explain your request, e.g. "change source repo to https://github.com/user123/repo123">
Registry Link: <link to your artifact on the Registry>
Request by: <the email associated with this request>

## Verification checklist

Please confirm the following by replacing `[ ]` with `[x]` where applicable:

- [ ] I have added the `.terraform-registry` file to the default branch of the current artifact repository
- [ ] I have added the `.terraform-registry` file to the default branch of the new repository (required for source repository changes)
- [ ] The `Request by` email in the file matches the email associated with this issue
- [ ] The registry link above points to the correct public registry artifact
- [ ] The new owner has already logged into the registry (required for ownership changes)

## Additional notes

- No action will be taken until ownership has been verified.
- Changes to artifact details may require direct administrative updates and are handled with extra caution.
- For provider source repository changes, verification can be completed through this issue template, but the internal change process may still require additional follow-up.

## Additional context

Add any other relevant details, links, or screenshots here.
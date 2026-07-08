# Pull Request

## Summary

Briefly describe what this Pull Request delivers.

This PR delivers only the main Jira ticket listed below.

## Main Jira ticket

Main ticket:

* `<JIRA-KEY>`

Rules:

* This PR must have exactly one main Jira ticket.
* The main Jira ticket must be referenced in the PR title.
* This PR delivers only the main Jira ticket.
* Related tickets may be listed for context only.

Expected PR title format:

```text
<type>(<scope>): <JIRA-KEY> <description>
```

Example:

```text
docs(readme): YLGOV-43 rewrite governance baseline
```

## Related tickets

List only tickets that are needed for context, dependencies, or traceability.

Related tickets are not delivered by this PR.

* `<JIRA-KEY>` -- reason for reference
* None

## Scope

Describe what is included in this PR.

Included:

* ...
* ...

Changed files / areas:

* `path/to/file.md`
* `path/to/other-file.md`

## Out of scope / Deferred

Describe what is intentionally not included in this PR.

Out of scope:

* ...
* ...

Deferred follow-up work:

* ...
* None

## Governance / Design Spec alignment

Select exactly one option:

* Design / Spec: `<JIRA-KEY>` -- approved Design / Spec
* No Design / Spec required -- reason: `<explain why this PR is inside existing approved scope or does not change governance, architecture, workflow, public API, or system behavior>`

Alignment checklist:

* [ ] This PR matches the main Jira ticket scope.
* [ ] This PR does not change governance rules unless approved by Design / Spec.
* [ ] This PR does not change architecture unless approved by Design / Spec.
* [ ] This PR does not change workflow unless approved by Design / Spec.
* [ ] This PR does not introduce unrelated scope.
* [ ] Related tickets are context only and are not delivered by this PR.

## Documentation impact

Select all that apply:

* [ ] Documentation was updated.
* [ ] Documentation update is not required.
* [ ] README was updated.
* [ ] Docusaurus / public docs were updated.
* [ ] Inline comments or local docs were updated.
* [ ] Follow-up documentation work is required.

Documentation notes:

* ...

## Testing / Verification

Select all that apply:

* [ ] Automated tests pass.
* [ ] New tests were added or updated.
* [ ] Manual verification was performed.
* [ ] Not applicable -- documentation-only or metadata-only change.

Verification details:

* Test environment:

  * ...

* Commands run:

  ```bash
  # example
  ```

* Manual verification steps:

  1. ...
  2. ...
  3. ...

## Review readiness checklist

Before requesting review, confirm:

* [ ] The PR title includes the main Jira ticket.
* [ ] This PR has exactly one main Jira ticket.
* [ ] The PR scope matches the main Jira ticket.
* [ ] Out-of-scope work is explicitly listed.
* [ ] Related tickets are clearly marked as context only.
* [ ] Design / Spec alignment is documented.
* [ ] Documentation impact is documented.
* [ ] Testing or verification is documented.
* [ ] No unrelated files are changed.
* [ ] No hidden governance, workflow, or architecture change is included.

## Merge requirements

This PR must be merged using Squash & Merge.

The final squash commit message must follow the YardaLab commit format:

```text
<type>(<scope>): <JIRA-KEY> <description>
```

Do not append the GitHub PR number to the squash commit message unless repository tooling explicitly requires it.

## Screenshots / Visuals

Attach screenshots, logs, or visual proof when relevant.

* Not applicable

## Notes

Add any context, trade-offs, risks, or follow-up notes.

* ...

**Reviewers**

Please tag the appropriate code owners or reviewers below:

@jarda-from-yardalab

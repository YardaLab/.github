# YardaLab .github

Organization-level GitHub defaults baseline for YardaLab.

## Purpose

This repository contains GitHub-facing default files for the YardaLab organization.

It provides a shared baseline for contribution guidance, pull request structure, community files, and repository-level governance documentation where GitHub supports organization-level defaults.

This repository helps keep YardaLab repositories consistent, reviewable, and easier to maintain.

## Governance relationship

This repository reflects YardaLab Governance v2.

It does not define governance.

Governance is defined by the YardaLab Operating Model, playbooks, and approved Jira Design / Spec work. This repository only exposes the GitHub-facing files that implement the approved baseline.

If this repository conflicts with the Operating Model, a playbook, or an approved Design / Spec, the approved governance source wins and this repository must be updated through Jira.

## Source of truth priority

YardaLab uses the following source of truth priority:

1. YardaLab Credo -- why the ecosystem exists.
2. YardaLab Engineering Principles -- how engineering decisions are evaluated.
3. YardaLab Operating Model -- system workflow and delivery model.
4. YardaLab Jira, Architecture, Documentation, and Contribution Playbooks -- execution rules.
5. Approved Jira Design / Spec tickets -- concrete decisions for a specific change.
6. Repository documentation -- local repository truth, including this README.
7. GitHub templates and tooling -- practical implementation and enforcement.

Tooling and templates must follow the approved governance documents.

They do not replace them.

## Jira-first workflow

Changes to this repository are managed in Jira first.

Expected flow:

```text
Idea / Epic / System Epic
-> Design / Spec when required
-> Documentation Draft when required
-> Task
-> Branch
-> Commit
-> Pull Request
-> Review
-> Merge
```

A change to this repository must have a scoped Jira Task.

If the change modifies governance, workflow, templates, cross-repository behavior, or source-of-truth rules, it must be backed by an approved Design / Spec before implementation starts.

GitHub is the delivery surface.

Jira remains the work management system.

## What this repository provides

This repository currently provides:

| Path                                         | Role                                 | Scope                                                                                                                                                     |
| -------------------------------------------- | ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `README.md`                                  | Repository overview                  | Explains the purpose, governance relationship, update rules, and boundaries of this repository.                                                           |
| `LICENSE`                                    | Repository license                   | Defines the license for this repository only. It is not an organization-wide default license file.                                                        |
| `.github/CONTRIBUTING.md`                    | Default contribution guidance        | Provides contribution guidance where GitHub applies organization-level defaults and a target repository does not provide its own file.                    |
| `.github/CODE_OF_CONDUCT.md`                 | Default code of conduct              | Provides community conduct guidance where GitHub applies organization-level defaults and a target repository does not provide its own file.               |
| `.github/PULL_REQUEST_TEMPLATE.md`           | Default pull request template        | Provides a default pull request body template where GitHub applies organization-level defaults and a target repository does not provide its own template. |
| `.github/ISSUE_TEMPLATE/universal-ticket.md` | Default fallback issue template      | Provides general public and fallback issue intake while keeping Jira canonical for planned work, governance, and delivery tracking.                       |
| `.github/CODEOWNERS`                         | Review ownership for this repository | Defines review ownership for this `.github` repository. It is not an organization-wide default `CODEOWNERS` file for every YardaLab repository.           |

## Repository structure

```text
.
├── README.md
├── LICENSE
└── .github/
    ├── ISSUE_TEMPLATE/
    │   └── universal-ticket.md
    ├── CODE_OF_CONDUCT.md
    ├── CODEOWNERS
    ├── CONTRIBUTING.md
    └── PULL_REQUEST_TEMPLATE.md
```

This structure must stay aligned with the actual repository contents.

If files are added, moved, or removed, this section must be updated in the same Pull Request.

## What this repository does not decide

This repository does not decide:

* YardaLab governance rules;
* Jira workflow states, validators, automations, or issue hierarchy;
* commit policy;
* branch policy;
* merge strategy;
* architecture rules;
* documentation tiers;
* project template rules;
* product scope;
* repository-specific exceptions;
* organization-wide license policy;
* organization-wide CODEOWNERS behavior.

Those decisions belong in the Operating Model, playbooks, and approved Jira Design / Spec tickets.

## Update rules

Every update to this repository must:

* have one main Jira Task as the delivery unit;
* stay inside the scope of that Task;
* reference the approved Design / Spec when required;
* update only files included in the Task scope;
* avoid unrelated template, workflow, or automation changes;
* preserve the source of truth priority;
* keep this README aligned with the actual repository structure;
* use the YardaLab commit format.

Commit format:

```text
<type>(<scope>): <TICKET> <description>
```

Example:

```text
docs(readme): YLGOV-43 rewrite governance baseline
```

Branch format:

```text
<type>/<TICKET>-<short-description>
```

Example:

```text
docs/YLGOV-43-github-readme-governance-baseline
```

## Local repository overrides

Individual YardaLab repositories may provide their own GitHub files when a repository-specific override is justified.

A local override must be:

* explicit;
* documented;
* reviewed through the Jira-first workflow;
* aligned with the Operating Model and playbooks;
* limited to the repository that needs it.

A local override must not silently weaken YardaLab governance.

If a local repository needs behavior that conflicts with this baseline, the reason must be documented and the relevant governance source must be updated or explicitly referenced.

## Maintenance checklist

Before merging a change to this repository, verify that:

* the Jira Task is in scope;
* required Design / Spec work is approved;
* no unrelated files were changed;
* this README still matches the repository structure;
* GitHub-facing files reflect current governance;
* no new governance rule was introduced without approved governance work;
* the Pull Request explains documentation impact;
* the final commit follows the YardaLab commit format.

## Notes

This repository exists to reduce repeated setup across YardaLab repositories.

It is a baseline, not a replacement for repository-specific documentation.

Repositories with product-specific behavior, build steps, runtime requirements, security models, or deployment processes must still document those details locally.

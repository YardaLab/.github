# Contributing to YardaLab

Thank you for contributing to YardaLab.

YardaLab uses a Jira-first, task-based delivery workflow designed to keep changes understandable, reviewable, and auditable.

This guide reflects YardaLab Governance v2.

It does not define governance.

The YardaLab Operating Model, Engineering Principles, approved playbooks, and approved Jira Design / Spec work remain the source of truth.

## 1. Code of Conduct

All contributors must follow the [Code of Conduct](CODE_OF_CONDUCT.md).

Be respectful, professional, and constructive in all project discussions, reviews, and contributions.

## 2. Contribution model

YardaLab separates decisions from implementation.

The typical production delivery flow is:

```text
Idea
-> Prototype when needed
-> Epic or System Epic
-> Design / Spec when required
-> Documentation Draft when required
-> Task
-> Branch
-> Commit
-> Pull Request
-> Review
-> Squash & Merge
-> DONE
```

For repository contributions, the delivery path is:

```text
Task
-> Branch
-> Commits
-> Pull Request
-> Review
-> Squash & Merge
-> DONE
```

A Pull Request is a delivery unit for one main Jira Task.

Implementation must stay inside the approved Task scope.

A Task must not silently change governance, architecture, workflow, public API, or other approved decisions.

## 3. Jira-first work management

Production work starts in Jira.

Before implementation begins, confirm:

* a Jira Task exists;
* the Task scope is clear;
* required dependencies are DONE;
* an approved Design / Spec exists when required;
* the planned change is inside the approved scope;
* the correct repository and files are identified.

Do not use GitHub issues, branches, commits, or Pull Requests as substitutes for required Jira decisions.

Git records implementation.

Jira records work management and delivery context.

Design / Spec records approved decisions.

## 4. Design / Spec guardrail

A Design / Spec is required when a change affects one or more of the following:

* governance rules;
* architecture;
* canonical workflow;
* public API;
* security model;
* ownership model;
* portability model;
* cross-repository behavior;
* ecosystem standards;
* shared templates or canonical behavior.

A Design / Spec is usually not required for:

* implementation details inside approved scope;
* small fixes;
* local refactoring without behavior change;
* documentation alignment with an already approved decision;
* isolated maintenance work without system impact.

If implementation reveals that an approved decision is incorrect or incomplete:

1. do not change the decision silently;
2. stop the affected implementation work;
3. update the Design / Spec or create explicit follow-up decision work;
4. update dependent Tasks when required.

A Pull Request must document its Design / Spec alignment or explain why no Design / Spec is required.

## 5. Prototype work

Prototype work is exploration, not production delivery.

A prototype may be used to:

* validate feasibility;
* test assumptions;
* explore unknown technology;
* reduce technical or workflow uncertainty;
* compare possible approaches.

Prototype work:

* must be isolated in a separate repository or approved experimental area;
* does not require the standard production contribution workflow;
* does not need to use production commit conventions;
* must not become a source of truth;
* must not bypass Design / Spec;
* must not be promoted directly into production.

Critical rule:

> Prototype code must not be promoted to production without refactoring.

When prototype findings are accepted, production implementation must continue through the standard Jira Task, branch, commit, Pull Request, review, and merge workflow.

## 6. Repository setup

Repository-specific setup instructions belong in the repository README or project documentation.

Typical setup:

```bash
git clone https://github.com/YardaLab/<repository-name>.git
cd <repository-name>
```

Install dependencies and development tooling according to the repository documentation.

Examples may include:

```bash
npm install
```

```bash
mix deps.get
```

Do not assume that every YardaLab repository uses the same language, runtime, package manager, or validation commands.

The repository README is the local source of truth for setup and development instructions.

## 7. Branches

Each Jira Task uses its own branch.

Branch format:

```text
<type>/<TICKET>-<short-description>
```

Examples:

```text
feature/YLC-12-add-login-flow
fix/YLT-8-correct-commit-validation
docs/YLGOV-44-align-contributing-guide-with-governance-v2
```

Branch rules:

* use one branch per main Jira Task;
* include the Jira ticket key;
* use a short and readable description;
* create the branch from the current target branch;
* keep unrelated work out of the branch;
* do not create a separate Pull Request for each Subtask.

Before creating a branch:

```bash
git switch main
git pull --ff-only
```

Create the Task branch:

```bash
git switch -c docs/YLGOV-44-align-contributing-guide-with-governance-v2
```

Repository-specific target branches may exist, but `main` is the default unless the repository explicitly documents another target.

Do not assume that a `develop` branch exists.

## 8. Commit messages

Commit messages must follow the YardaLab commit format:

```text
<type>(<scope>): <TICKET> <description>
```

Example:

```text
docs(contributing): YLGOV-44 align contributing guide with governance v2
```

Additional examples:

```text
feat(auth): YLC-12 add login endpoint
fix(ci): YLT-18 correct commit validation workflow
refactor(events): YLC-42 simplify event dispatch
test(sessions): YLC-55 add refresh token coverage
```

Commit messages must:

* use an allowed type;
* include a meaningful scope;
* include the main Jira ticket key;
* use a concise description;
* describe the actual change;
* remain readable after Squash & Merge.

### Allowed commit types

| Type       | Purpose                                   |
| ---------- | ----------------------------------------- |
| `feat`     | New functionality                         |
| `fix`      | Bug fix                                   |
| `docs`     | Documentation change                      |
| `chore`    | Non-functional maintenance                |
| `refactor` | Structural change without behavior change |
| `test`     | Test additions or updates                 |
| `build`    | Build system or dependency changes        |
| `ci`       | CI/CD configuration                       |
| `perf`     | Performance improvement                   |
| `revert`   | Revert of a previous change               |

Do not use unapproved commit types.

For example, `style` is not part of the current YardaLab allowed commit type list.

Tooling may validate commit messages locally or in CI.

Tooling enforces governance rules.

Tooling does not define them.

## 9. Pull Requests

Every production change to the canonical repository must use a Pull Request.

A Pull Request belongs to one main Jira Task.

The PR title must follow the YardaLab commit format:

```text
<type>(<scope>): <TICKET> <description>
```

Example:

```text
docs(contributing): YLGOV-44 align contributing guide with governance v2
```

### One main Jira ticket

Each PR must have exactly one main Jira ticket.

The PR delivers only that ticket.

Related tickets may be included only when required for:

* dependency context;
* Design / Spec traceability;
* parent Epic or System Epic context;
* understanding the change.

Related tickets are context only.

They are not delivered by the PR.

### PR scope

The Pull Request must clearly document:

* summary;
* main Jira ticket;
* included scope;
* out-of-scope or deferred work;
* Design / Spec alignment;
* documentation impact;
* testing or verification;
* review readiness;
* relevant notes or risks.

Do not combine unrelated Jira Tasks in one Pull Request.

Do not expand Task scope silently during implementation.

## 10. Pull Request review

Before requesting review, confirm:

* the PR title includes the main Jira ticket;
* the PR has exactly one main Jira ticket;
* the implementation matches the Task scope;
* dependencies are DONE or explicitly documented;
* Design / Spec alignment is documented;
* related tickets are context only;
* out-of-scope work is explicit;
* tests were added or updated where relevant;
* documentation was updated where relevant;
* no unrelated files are changed;
* no hidden governance, workflow, or architecture change is included;
* no blocking open questions remain.

Review should verify:

* scope alignment;
* correctness;
* documentation impact;
* test or verification evidence;
* architecture alignment;
* governance guardrails;
* maintainability.

Pull Request review is the delivery gate.

Review does not replace Design / Spec approval.

## 11. Testing and verification

Every change must include appropriate verification.

The exact commands depend on the repository.

Examples for Node.js projects:

```bash
npm run lint
npm test
```

Examples for Elixir projects:

```bash
mix format --check-formatted
mix test
```

Documentation-only or metadata-only changes may not require automated tests.

They still require relevant manual verification.

Possible documentation verification:

```bash
git status --short
git diff -- .github/CONTRIBUTING.md
```

These commands help verify:

* only expected files changed;
* the exact documentation diff was reviewed;
* no unrelated work entered the Task scope.

Testing and verification must be documented in the Pull Request.

Do not mark unavailable or irrelevant tests as completed.

Use an explicit explanation when testing is not applicable.

## 12. Documentation expectations

Documentation is part of the product.

Documentation must be updated when a change affects:

* public behavior;
* API contracts;
* developer workflow;
* user workflow;
* setup instructions;
* architecture;
* configuration;
* governance-facing repository behavior.

Documentation must reflect the actual implementation.

A change is not complete when:

* documentation describes behavior that does not exist;
* implemented behavior is missing from required documentation;
* examples are outdated;
* setup instructions no longer work;
* repository structure documentation is incorrect.

The appropriate documentation level depends on the project.

Examples:

* repository or module guidance -> `README.md`;
* local development guidance -> repository Markdown documentation;
* public user or integration documentation -> published documentation;
* deep architectural explanation -> architecture reference documentation.

Do not assume every project uses the same documentation structure.

Follow the repository README and the YardaLab Documentation Playbook.

## 13. Squash & Merge

YardaLab uses Squash & Merge for canonical delivery.

The final squash commit must follow:

```text
<type>(<scope>): <TICKET> <description>
```

Example:

```text
docs(contributing): YLGOV-44 align contributing guide with governance v2
```

Before confirming the merge:

* verify the final squash commit message;
* preserve the main Jira ticket key;
* remove automatically appended text that violates the commit format;
* leave the extended commit description empty unless useful context is required;
* confirm that the PR passed review;
* confirm that required checks passed.

Do not use:

* direct push to `main`;
* merge commits;
* rebase merge into `main`;
* squash commits without a Jira ticket key.

After merge, the Jira Task may proceed to DONE only when delivery verification is complete.

## 14. Definition of Done

A contribution is complete when:

* the implementation matches the Jira Task;
* required dependencies are resolved;
* Design / Spec alignment is preserved;
* tests or verification are complete;
* documentation reflects reality;
* review feedback is resolved or explicitly deferred;
* required checks pass;
* the Pull Request is merged;
* the final squash commit follows YardaLab commit conventions;
* no blocking questions remain.

A Task is DONE only after the change is delivered.

An open Pull Request is not DONE.

An approved but unmerged Pull Request is not DONE.

## 15. Out-of-scope and alignment findings

When unrelated work or governance misalignment is discovered:

* do not hide it;
* do not silently expand the current Task;
* do not modify governance rules inside an unrelated PR;
* document the finding;
* create a separate alignment Task when required;
* complete the current Task only inside its approved scope.

The goal is not bureaucracy.

The goal is to preserve understandable and auditable delivery.

## 16. Issue reporting

When reporting a problem or proposing work, include relevant information such as:

* problem or opportunity;
* expected behavior;
* actual behavior;
* steps to reproduce when applicable;
* environment details;
* logs, screenshots, or evidence;
* affected repository, module, or workflow.

Significant work must continue through the appropriate Jira governance workflow.

## 17. License

By contributing to this repository, you agree that your contributions are licensed under the same license as the repository.

See the repository [LICENSE](../LICENSE).

## 18. Summary

YardaLab contribution flow:

```text
Jira Task
-> Branch
-> Commits
-> Pull Request
-> Review
-> Squash & Merge
-> DONE
```

Core rules:

* one main Jira Task per Pull Request;
* Design / Spec before implementation when required;
* no silent scope expansion;
* documentation reflects reality;
* tests or verification are required;
* related tickets are context only;
* prototype work is not production delivery;
* Pull Requests use Squash & Merge;
* the final commit follows the YardaLab commit format.

Think before building.

Document before implementing.

Verify before merging.

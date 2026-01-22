# Contributing Guidelines

Thank you for your interest in contributing to this repository.
Please take a moment to read the following guidelines to ensure a smooth contribution process.

---

## 1. Code of Conduct
All contributors must adhere to the [Code of Conduct](CODE_OF_CONDUCT.md). Be respectful and professional in all interactions.

---

## 2. Getting Started

### Repository Setup
1. Fork this repository to your account.
2. Clone your fork locally:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   ```
3. Create a new branch based on the feature or issue you're addressing:
   ```bash
   git checkout -b feature/your-feature-name
   ```

### Development Requirements
- Node.js LTS or Elixir (depending on project type)
- npm / mix
- Prettier and ESLint (configured in repo)
- Husky hooks installed via `npm install` or `mix deps.get`

---

## 3. Commit Messages
Follow the commit message conventions used in this project. Each commit should include a type and ticket reference if applicable:

```
<type>(<scope>): <short description>
```

**Examples:**
```
feat(core): add session synchronization over WebSocket
fix(docs): correct link to authentication overview
chore(infra): update Terraform provider version
```

Allowed types:
- `feat` – new feature
- `fix` – bug fix
- `docs` – documentation only changes
- `style` – formatting or style-related changes
- `refactor` – code change that neither fixes a bug nor adds a feature
- `test` – adding or fixing tests
- `chore` – maintenance tasks

---

## 4. Branch Naming
Use this pattern for branches:
```
<type>/<ticket-id>-<short-description>
```
Example:
```
feature/IYI-3-create-github-repository
```

---

## 5. Pull Requests

### Checklist before submitting a PR
- [ ] Code builds and all tests pass locally.
- [ ] The implementation aligns with acceptance criteria.
- [ ] Documentation updated if necessary.
- [ ] Commit messages follow the format.
- [ ] Title includes the related Jira ticket ID if applicable.

### Review Process
1. Open a Pull Request targeting the `develop` branch (or `main` if otherwise specified).
2. Provide a clear title and description summarizing the changes.
3. Link related issues or Jira tickets.
4. Wait for review from the code owners (see `CODEOWNERS`).
5. Address review comments as needed.

---

## 6. Testing and Linting
Before pushing your changes:
```bash
npm run lint
npm test
```
Or for Elixir projects:
```bash
mix format --check-formatted
mix test
```

---

## 7. Documentation Updates
When modifying or adding functionality, update documentation under `docs/` following the structure defined in `docsstyle.md`.
Each page should follow the standard sectioning and metadata described there.

---

## 8. Issue Reporting
When reporting a bug or requesting a feature, please include:
- Steps to reproduce or a clear use case.
- Expected vs actual behavior.
- Environment details (Node version, OS, etc.).
- Relevant logs or screenshots if applicable.

---

## 9. License
By contributing to this repository, you agree that your contributions will be licensed under the same license as the project (see `LICENSE`).

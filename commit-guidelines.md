This document defines the standard for writing commit messages in the project. We use the **Conventional Commits** format to ensure clarity, consistency, and compatibility with changelog automation tools.

* * *

## ✅ Why Follow a Commit Convention?

-   Keeps commit history organized and readable
-   Makes it easier to generate changelogs
-   Enables automatic versioning (Semantic Release, etc.)
-   Helps team members understand the purpose of a change at a glance
* * *

## 📒 Commit Message Format

Each commit message should follow this structure:

```
type(scope): short description

[optional body]
[optional footer]
```

### ✉️ Examples

```
feat(auth): add Google login with Supabase
fix(rsvp): fix confirmation status not updating
refactor(dashboard): simplify guest count logic
docs(readme): update setup instructions for Tailwind 4
```

* * *

## ⚖️ Allowed Types

| Type | Description |
| --- | --- |
| `feat` | New feature |
| `fix` | Bug fix or patch |
| `refactor` | Code refactor that doesn't add/remove features |
| `docs` | Documentation changes only |
| `style` | Formatting only (whitespace, semicolons, etc.) |
| `test` | Adding or updating tests |
| `chore` | Other changes (build, config, tooling, etc.) |

* * *

## 🎨 Scope (optional but encouraged)

Use a short, lowercase scope in parentheses to indicate the affected area of the codebase. Examples:

-   `auth`
-   `rsvp`
-   `dashboard`
-   `api`
-   `guests`
-   `styles`
* * *

## 📚 Body (when needed)

Use the body to explain **what** and **why** in more detail if the change isn't obvious. Keep it concise.

* * *

## ♻️ Footer (for special cases)

Use footers only for things like breaking changes or linked issues:

```
BREAKING CHANGE: updated RSVP link format
Closes #42
```

* * *

## 🔧 Best Practices

-   Commit **early and often**, but keep commits focused
-   Avoid large "catch-all" commits
-   Use present tense: "add feature" not "added feature"
-   Use imperative mood: "fix bug" not "fixes bug"
-   Capitalize message after the colon (optional, but preferred)

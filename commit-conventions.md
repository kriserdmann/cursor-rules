# Commit Conventions – Micro SaaS RSVP

## 🧠 You are working on a professional-grade Micro SaaS project.

All commits must follow a **semantic, consistent, and descriptive format** to ensure clarity in collaboration, maintainability, and versioning.

---

## 🧾 Commit Message Format

Each commit message must follow this structure:

```txt
<type>(optional-scope): <short-description>

[optional body]

[optional footer(s)]


---

## ✅ Common Commit Types

| Type       | Purpose                                                              |
|------------|----------------------------------------------------------------------|
| `feat`     | A new feature                                                        |
| `fix`      | A bug fix                                                            |
| `docs`     | Documentation changes only                                           |
| `style`    | Changes that do not affect logic (whitespace, formatting, etc.)     |
| `refactor` | Code change that neither fixes a bug nor adds a feature             |
| `perf`     | Performance improvements                                             |
| `test`     | Adding or updating tests                                             |
| `chore`    | Maintenance tasks (e.g., config updates, build tools, dependencies) |
| `ci`       | Changes to CI/CD configuration files and scripts                    |
| `revert`   | Reverts a previous commit                                            |

---

## 🧩 Scope (Optional)

You can specify a scope to clarify what part of the project was affected.  
Use lowercase and dash-separated words.

**Examples:**

- `feat(events): add event duplication feature`
- `fix(guests): handle missing contact info`
- `style(auth-form): update button spacing`
- `refactor(lib/supabase): extract helper functions`

---

## 🧾 Description Guidelines

- Use the **imperative** mood in the short description (e.g., `add`, `fix`, not `added`, `fixed`)
- Keep the **short description under 72 characters**
- Avoid generic messages like `update code`, `fix stuff`, etc.

---

## 📝 Commit Body (Optional)

Use the body when:

- Explaining **what** and **why** (not just how)
- Providing context for design decisions
- Listing known trade-offs or future improvements

Break lines at 100 characters for readability.

---

## 🔖 Footer (Optional)

Used for:

- Breaking changes (`BREAKING CHANGE:` prefix)
- Linking issues or pull requests (`Closes #123`, `Refs #456`)


---

## 🚀 Best Practices

- Commit often, but logically (atomic commits)
- Group related changes together
- Avoid mixing formatting changes with logic changes
- Always lint and test before committing

---

> Use these conventions to keep the Git history clean, searchable, and maintainable.

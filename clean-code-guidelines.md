These clean code guidelines are intended to keep the project readable, maintainable, scalable, and collaborative. The goal is to make your code a pleasure to revisit — even months later.

* * *

## 🧠 1. General Philosophy

-   **Clarity over cleverness** – Write code for humans, not just for the compiler.
-   **Consistency is key** – Stick to agreed naming, structure, and formatting patterns.
-   **Make it obvious** – Avoid surprises or ambiguous behaviors.
-   **Small, single-purpose units** – Keep components and functions focused.
* * *

## 📁 2. File and Folder Structure

-   Use **clear, flat structure** inside `/src`
-   Organize by **feature or responsibility**, not file type
-   Example:

    ```
    /components/
      EventForm.js
      GuestTable.js

    /app/
      eventos/
        [id]/page.js
        novo/page.js
    ```

* * *

## ✍️ 3. Naming Conventions

-   **Use descriptive names** for files, variables, functions, and components.
-   Prefer clarity: `handleSendReminder()` > `handleClick()`
-   Files and folders: kebab-case (e.g., `guest-table.js`)
-   Components: PascalCase (e.g., `GuestCard`)
-   Variables: camelCase (e.g., `guestList`, `eventTitle`)
* * *

## 🔀 4. Components

-   Keep components **small and focused** (max 150 lines when possible)
-   Split into **presentational (UI-only)** and **container (logic)** when needed
-   Use props clearly: document them and avoid magic booleans
-   Extract repetitive UI patterns into reusable components
* * *

## 🧪 5. Functions & Logic

-   Functions should do **one thing only**
-   Keep them pure whenever possible
-   Limit to **max 3–4 parameters**
-   Prefer early returns over deeply nested `if`/`else`
-   Name functions with action verbs: `sendInvite`, `filterGuests`, `exportToPDF`
* * *

## 🎯 6. Code Style & Formatting

-   Use Prettier and ESLint consistently across the project
-   Follow Airbnb or Next.js ESLint rules with Tailwind plugin
-   Break long lines and avoid complex ternaries
-   Use Tailwind classes in **logical, layered order**:

    ```
    Layout → Spacing → Typography → Color → State
    ```

* * *

## 🧹 7. Tailwind-Specific Tips

-   **Avoid duplicating utility chains** — extract into class groups/components
-   Use semantic HTML (e.g., `<button>`, `<section>`, `<form>`)
-   Group related classes together for readability:

    ```
    class="flex items-center justify-between px-4 py-2 bg-white shadow-sm"
    ```

* * *

## 🔐 8. API & Database Interactions

-   Use a dedicated file for Supabase functions (e.g., `/lib/supabase.js`)
-   Wrap fetch/database calls in try/catch blocks
-   Keep Supabase row-level access rules enforced
-   Abstract repetitive logic (like confirmation updates) into utilities
* * *

## 🧼 9. Comments & Documentation

-   **Don’t comment the obvious** – make the code explain itself
-   Use comments for **why**, not **what**
-   For complex logic, add 1–2 lines of context above the function
-   Keep README and internal docs updated as features evolve
* * *

## 🔄 10. Refactor Often

-   Refactor when:
    -   A function/component does too much
    -   There’s duplicated logic
    -   Naming is unclear
-   Small improvements over time lead to sustainable code
* * *

## ✅ Final Tips

-   Think like a new developer joining the team.
-   If something feels confusing, write it better.
-   The best code is **easy to delete and rebuild**.
* * *

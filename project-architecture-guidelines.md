# Project Architecture Guidelines – Micro SaaS RSVP

## 🧠 You are an expert full-stack developer with experience in scalable architecture, clean code, and maintainable folder structures using Next.js (App Router), TailwindCSS 4, Supabase, and modern web standards.

All decisions regarding folder structure, component design, and data flow must follow these architectural principles.

---

## 🛡 Project Architecture Goals

- Ensure a clean, modular, and scalable architecture that supports long-term maintainability.
- Maximize separation of concerns across features and layers.
- Follow a clear and consistent file/folder structure using Next.js App Router.

---

## 📁 Directory Structure (App Router)

```bash
src/
├── app/
│   ├── layout.tsx              # Root layout
│   ├── page.tsx                # Dashboard (home page)
│   ├── eventos/
│   │   ├── novo/page.tsx       # New event form
│   │   ├── [id]/page.tsx       # Event management
│   ├── api/
│   │   ├── guests/sendMessage.ts   # Send WhatsApp/email
│   │   ├── guests/confirm.ts       # RSVP endpoint
│   │   ├── reports/export.ts       # Export to PDF/CSV
├── components/                 # Shared UI components
│   ├── EventForm.tsx
│   ├── GuestTable.tsx
│   ├── DashboardStats.tsx
│   ├── ConfirmationPage.tsx
│   ├── PDFButton.tsx
├── lib/                        # Supabase client, helpers
├── types/                      # TypeScript types/interfaces
├── constants/                  # Static config or enums
├── hooks/                      # Custom React hooks
├── styles/                     # Global and custom styles

## ✅ Design Principles

- **Feature-first**: Group code by feature where applicable (e.g., `/eventos`, `/guests`).
- **Separation of concerns**: Keep UI components separate from business logic and data fetching.
- **Single Responsibility**: Each component, hook, or helper should do one thing only.
- **Declarative data flow**: Use hooks and composables instead of imperative logic.
- **Avoid tight coupling**: Keep Supabase or third-party services abstracted in the `lib/` folder.

---

## 🧱 Component Organization

Components should be:

- Reusable and composable  
- Written in TypeScript with strong typing  
- Styled with TailwindCSS (no inline styles or CSS modules)  
- Placed in `/components` or in a `/[feature]/components` subfolder if specific  

---

## 📦 Supabase Integration

- Supabase client should be initialized in a single file (e.g., `lib/supabase.ts`).
- All database operations must be encapsulated in helper functions.
- Authentication logic should be centralized and use server-side protection when applicable.

---

## 🌐 API Structure (Next.js App Router)

- Use `app/api/` for custom API routes.
- Keep logic in API handlers concise — delegate to `lib/` for actual business logic.
- Ensure proper error handling and validation using **Zod**.

---

## 🧪 Testing and Validation

- Use **TypeScript** everywhere.
- Validate API inputs with **Zod**.
- *(Optional)* Use **Playwright** or **Vitest** for automated testing later.

---

## 🌍 Localization

- Structure for internationalization (i18n) must be prepared from the start.
- Use **English** for all internal code, comments, and keys.
- Default language on UI: **Portuguese**, with future support for English and Spanish.

---

## 📌 Best Practices

- Prefer **Server Components** when possible.
- Use **dynamic imports** to improve performance.
- Avoid unnecessary **client-side rendering**.
- Implement loading, error, and empty states for all async UI.
- Avoid repetition — extract shared logic into utilities or custom hooks.


# Frontend Guidelines – Micro SaaS RSVP

## 🧠 You are a frontend specialist with deep knowledge of modern web development using Next.js (App Router), TailwindCSS 4, React Server Components, and accessibility standards.

All frontend code should be written in TypeScript and structured to prioritize clarity, maintainability, performance, accessibility, and responsive design.

---

## 📅 Tech Stack

- **Framework**: Next.js with App Router  
- **Styling**: Tailwind CSS 4  
- **UI Libraries**: shadcn/ui, Radix UI (as needed)  
- **Language**: TypeScript (no JavaScript files)  
- **Icons**: Lucide or similar SVG-based icon libraries  
- **Data**: Supabase for API and storage  

---

## ✅ General Principles

- Follow a **mobile-first** design approach.  
- Write clean and **semantically correct HTML**.  
- Use **functional components** only – avoid class components.  
- Follow accessibility guidelines (WCAG 2.1 AA).  
- Keep components **pure** and **stateless** when possible.  
- Prefer **React Server Components (RSC)**; only use `'use client'` when needed.  
- Use **TypeScript types** everywhere (Props, API responses, etc).  

---

## 🌍 Internationalization (i18n)

- UI must support multiple languages.  
- Codebase must be in **English**, default language on the interface is **Portuguese**.  
- Use `app/[lang]/` route segments in Next.js to support language switch.  
- Extract static text into a centralized i18n system (JSON or TS objects).  

---

## 👥 Component Design

- Components should be:  
  - **Reusable, testable, and isolated**  
  - Use **shadcn/ui** components with Tailwind overrides where necessary  
  - Avoid unnecessary prop drilling – use context providers or shared hooks  
  - Have a single purpose (SRP – Single Responsibility Principle)  
  - Placed in organized folders (e.g., `components/events/`)  

---

## 🧵 Styling Rules

- Use **TailwindCSS utility classes only** (no external CSS/styled-components).  
- Prefer `@apply` and Tailwind variants for reuse.  
- Organize shared styles in `styles/`, constants in `constants/`, and helpers in `lib/`.  
- Use semantic color naming conventions (e.g., `text-danger`, `bg-accent`).  

---

## ♿ Accessibility (a11y)

- Use semantic tags: `button`, `form`, `label`, `section`, etc.  
- Apply `aria-*` attributes when needed.  
- Ensure full **keyboard navigation** for all interactive elements.  
- Test with **screen readers** and color contrast tools.  
- Add `alt` text to all images and icons.  

---

## ⚡ Performance

- Favor server-side rendering (RSC/SSR).  
- Use dynamic imports (`next/dynamic`) to reduce JS bundle size.  
- Optimize all images with `next/image` and lazy loading.  
- Remove unused Tailwind classes with PurgeCSS.  

---

## 🖌 UX Guidelines

- Follow **Nielsen's 10 Usability Heuristics**.  
- Provide **loading indicators** during async operations.  
- Offer **clear feedback** for user actions.  
- Prevent user errors with form validation and confirmation prompts.  
- Use consistent spacing, color hierarchy, and visual rhythm.  

---

## 🧾 Forms and Validation

- Use `react-hook-form` for form handling and `zod` for validation.  
- Include real-time feedback for inputs.  
- Group fields logically with `fieldset` and `legend`.  
- Mark required fields and display validation messages clearly.  

---

## 📊 Analytics and Feedback (Optional)

- Track basic user actions (e.g., confirmation clicks, form errors).  
- Optionally integrate tools like Hotjar or Microsoft Clarity.  

---

## 🔍 QA and Testing

- Test responsiveness using browser devtools and actual devices.  
- Ensure minimum tap target size: **44x44px**.  
- Run automated accessibility checks using Lighthouse and axe.  

---

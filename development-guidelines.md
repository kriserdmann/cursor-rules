This guide outlines best practices, conventions, and standards for building modern web applications using technologies such as **React.js, Next.js, TypeScript, Redux, HTML, CSS, and Tailwind CSS**, with a focus on clean architecture, performance, accessibility, and maintainability.

* * *

## 💡 Development Philosophy

-   Write clean, maintainable, and scalable code
-   Follow **SOLID** principles
-   Emphasize **functional** and **declarative** programming
-   Prioritize **type safety** and static analysis
-   Practice **component-driven development**
* * *

## 📐 Code Implementation Guidelines

### Planning Phase

-   Begin with **step-by-step planning**
-   Write **detailed pseudocode** before implementation
-   Document **component architecture** and **data flow**
-   Consider **edge cases** and **error scenarios**
* * *

### Code Style

-   Use **tabs** for indentation
-   Use **single quotes** for strings (except when escaping is needed)
-   **Omit semicolons** (unless required for disambiguation)
-   Eliminate **unused variables**
-   Add spaces:
    -   After keywords (`if`, `for`, `while`)
    -   Before function declaration parentheses
    -   After commas and around infix operators
-   Keep `else` on the **same line** as the closing curly brace
-   Use **curly braces** for multi-line conditionals
-   Always handle **error parameters** in callbacks
-   Limit line length to **80 characters**
-   Use **trailing commas** in multiline object/array literals
* * *

## 🧾 Naming Conventions

### General Rules

| Format | Use For |
| --- | --- |
| PascalCase | Components, Type Definitions, Interfaces |
| kebab-case | File and directory names (e.g. `auth-wizard.tsx`) |
| camelCase | Variables, Functions, Hooks, Props, Methods |
| UPPERCASE | Environment variables, Global constants |

### Specific Patterns

-   Event handlers: `handleClick`, `handleSubmit`
-   Boolean values: `isLoading`, `hasError`, `canSubmit`
-   Custom hooks: `useAuth`, `useForm`
-   Prefer **full words** over abbreviations, with exceptions: `err`, `req`, `res`, `props`, `ref`
* * *

## ⚛️ React Best Practices

### Component Architecture

-   Use **functional components** with **TypeScript interfaces**
-   Prefer `function` keyword over arrow functions for components
-   Extract reusable logic into **custom hooks**
-   Practice **component composition**
-   Use `React.memo` for performance-sensitive components
-   Always perform **cleanup** in `useEffect` hooks

### Performance Optimization

-   Use `useCallback` to memoize callbacks
-   Use `useMemo` for expensive computations
-   Avoid **inline functions** in JSX
-   Use **code splitting** via `dynamic import`
-   Always use meaningful **key props** in lists (avoid using index)
* * *

## 🔀 Next.js Best Practices

### Core Concepts

-   Use **App Router**
-   Implement proper **metadata** and SEO handling
-   Apply **caching strategies** thoughtfully
-   Handle errors with **error boundaries**

### Components & Features

-   Prefer built-in Next.js components:
    -   `<Image>` for optimized images
    -   `<Link>` for routing
    -   `<Script>` for 3rd-party scripts
    -   `<Head>` for metadata
-   Implement proper **loading states**
-   Use the correct **data fetching method** (server-side, static, or client)

### Server Components

-   Default to **server components**
-   Use **URL query parameters** for server state
-   Use `'use client'` directive only when necessary:
    -   Event listeners
    -   State management
    -   Browser APIs
    -   Client-side-only libraries
* * *

## 🧩 TypeScript Standards

-   Enable **`strict` mode**
-   Define **clear interfaces** for props, state, Redux slices
-   Use **type guards** for null/undefined checks
-   Apply **generics** where flexibility is needed
-   Leverage **utility types**: `Partial`, `Pick`, `Omit`
-   Prefer `interface` over `type` for extendable structures
-   Use **mapped types** to create dynamic type variations
* * *

## 🎨 UI & Styling Guidelines

### Component Libraries

-   Use **Shadcn UI** for consistent, accessible components
-   Leverage **Radix UI** for low-level, accessible primitives
-   Apply **composition patterns** for modular UI

### Styling with Tailwind CSS

-   Use **Tailwind CSS v4** for utility-first styling
-   Follow **mobile-first** responsive design
-   Implement **dark mode** with Tailwind or CSS variables
-   Ensure **color contrast** meets accessibility standards
-   Maintain **consistent spacing** for visual rhythm
-   Define **CSS variables** for theme support
* * *

## 🌐 State Management

### Local State

-   Use `useState` for simple state
-   Use `useReducer` for complex state
-   Use `useContext` for lightweight global state

### Global State

-   Use **Redux Toolkit** as default
-   Define slices with `createSlice`
-   Normalize deeply nested data
-   Use **selectors** for data access abstraction
-   Split state into **feature-specific slices**
* * *

## 🛑 Error Handling & Validation

### Forms

-   Use **Zod** for schema validation
-   Use **React Hook Form** for efficient form handling
-   Display clear and accessible **error messages**

### Runtime Errors

-   Use **Error Boundaries** to gracefully catch UI errors
-   Log errors to services like **Sentry**
-   Provide helpful **fallback UIs**
* * *

## 🧪 Testing Strategy

### Unit Testing

-   Use **Jest** and **React Testing Library**
-   Follow **Arrange–Act–Assert** pattern
-   Mock APIs and external dependencies
-   Avoid overuse of snapshot testing

### Integration Testing

-   Focus on **end-user workflows**
-   Properly set up and tear down test states
-   Use `screen` from RTL for queries
* * *

## ♿ Accessibility (a11y)

-   Use **semantic HTML**
-   Apply **ARIA attributes** when necessary
-   Support **keyboard navigation**
-   Manage **focus and tab order**
-   Ensure **sufficient color contrast**
-   Follow a logical **heading structure**
-   Make **interactive elements fully accessible**
-   Show **accessible error messages**
* * *

## 🔐 Security Best Practices

-   Sanitize user input to prevent **XSS**
-   Use **DOMPurify** for HTML sanitation
-   Use secure **authentication flows**
* * *

## 🌍 Internationalization (i18n)

-   Use **next-i18next** for translation
-   Implement **locale detection**
-   Format **dates, currencies, and numbers** properly
-   Ensure **RTL** layout support when needed
* * *

## 📝 Documentation Standards

-   Use **JSDoc** or TypeScript annotations
-   Document:
    -   Public functions, methods, components, types
    -   Use clear and complete sentences
    -   Add usage examples where helpful
-   Use proper Markdown:
    -   Headings, code blocks, links, lists


# Project Guidelines for Confirmação Simplificada de Presença

## Language and Localization
- **Codebase Language:** All code, comments, and documentation must be in English.
- **Localization:** The application should support multiple languages, with Portuguese as the default.

## Technologies and Frameworks
- **Frontend:** Utilize Next.js with the App Router feature.
- **Styling:** Implement Tailwind CSS v4 for responsive and consistent UI design.
- **Backend Services:** Use Supabase for authentication, database management, and storage.
- **Communication:** Integrate Twilio Sandbox for WhatsApp messaging and EmailJS/Resend for email services.
- **PDF Generation:** Employ html2pdf.js for exporting reports.

## Code Structure and Organization
- **Componentization:** Develop reusable React components to promote maintainability.
- **File Naming:** Use lowercase with hyphens for directory names (e.g., `components/auth-wizard`).
- **State Management:** Leverage React's built-in state management; consider external libraries if necessary.

## Best Practices
- **Error Handling:** Implement comprehensive error handling and validation, prioritizing early returns and guard clauses.
- **Security:** Ensure proper validation of user inputs and implement secure coding practices.
- **Performance:** Optimize images using WebP format, include size attributes, and implement lazy loading. Minimize the use of `'use client'`, `useEffect`, and `setState`; favor React Server Components (RSC) and Next.js SSR features.
- **Testing:** Write unit tests using Jest and React Testing Library. Ensure all critical paths are covered.

## Version Control and Collaboration
- **Commits:** Use semantic commit messages (e.g., `feat: add event creation form`).
- **Branching:** Follow a consistent branching strategy, such as Git Flow.
- **Code Reviews:** Require code reviews for all pull requests to maintain code quality.

## Documentation
- **README:** Maintain an up-to-date `README.md` with clear setup and usage instructions.
- **Comments:** Provide clear and concise comments for complex logic and use JSDoc comments for functions and components to improve IDE intellisense.


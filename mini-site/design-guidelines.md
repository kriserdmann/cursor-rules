# Design Guidelines – Digital Card & Mini Site Creator

## 🎨 Visual Style
- **Framework**: Tailwind CSS v4 with Preline UI (Installing Tailwind CSS as a PostCSS plugin is the most seamless way to integrate it with frameworks)
- **Look & Feel**: Modern, minimal, clean
- **Inspiration**: Vercel dashboard, Notion, Stripe landing pages
- **Default Palette**: Soft gradients, neutral background with vibrant CTA highlights
- **Typography**: Sans-serif fonts (e.g. Inter or DM Sans)
- **Cards**: Rounded corners, subtle shadows, clean spacing

## 📐 Layout Principles
- Mobile-first design (80% of users via WhatsApp/mobile)
- Grid layout for dashboard
- Sticky headers and floating CTAs where useful
- Use Preline UI cards, modals, and input groups for consistency

## 🧑‍💻 Accessibility & Responsiveness
- WCAG 2.1 compliant color contrasts
- Keyboard navigation and focus states
- Responsive across iOS, Android, and small devices
- Tap-friendly buttons (min 44px height)

## 🧠 UX Considerations
- Minimize steps to publish a card
- Real-time preview on form edits
- Clear success states ("Link created! QR ready")
- Friendly onboarding for first-time users

## 🎤 Brand Tone & Voice
- Friendly and helpful
- Actionable microcopy ("Add your link", "Tap to preview")
- Localized Portuguese support down the road (i18n-ready)


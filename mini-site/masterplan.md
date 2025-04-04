Masterplan: Digital Card & Mini Site Creator (SaaS)

🧭 Overview & Objectives

Create a lightweight, accessible SaaS platform that empowers small businesses and independent professionals to easily build and share personalized digital business cards and mini sites. The cards serve as mobile-friendly landing pages with profile info, key links, and QR code sharing.

👥 Target Audience

Small businesses and freelancers (e.g., hairdressers, barbers, local shops, coaches, content creators)

Users with minimal technical skills

Those who promote themselves through WhatsApp, Instagram, Facebook and want a shareable online presence

💡 Core Features

Google login authentication

Card creation dashboard with preview

Profile customization (image, name, description)

Add links (WhatsApp, Instagram, Facebook, website, email)

Select color palette and typography

Optional payment button (Pix or Mercado Pago)

Auto-generated QR Code (PNG/PDF)

Mobile-first mini site with unique URL

View access statistics (views, link clicks)

🧱 Tech Stack

Frontend: Next.js (App Router, JavaScript)

Backend/API: Supabase (Database, Storage, Auth)

UI Framework: Tailwind CSS v4 + Preline UI components

QR Code API: QRCode Monkey or Google Charts API

Analytics: Google Analytics API (for basic link/click stats)

Hosting: Vercel

📊 Conceptual Data Model

Users

id

email

name

profile_image

created_at

Cards

id

user_id (foreign key)

business_name

profile_image_url

description

links (array: {type, url})

theme_color

font

qr_code_url

unique_slug

stats_enabled (boolean)

created_at

updated_at

Stats (optional)

id

card_id

event_type ("view", "click")

target ("whatsapp", "instagram", etc.)

timestamp

🎨 UI/UX Principles

Clean, minimal, modern (Preline UI style)

Tailwind v4 utility-first styling

Responsive, mobile-first layouts

Intuitive forms and preview interactions

Emphasis on simplicity and fast sharing

🔒 Security Considerations

Use Supabase Auth for secure user sign-in

Ensure only the card owner can edit/delete their content

Sanitize all user-generated input (especially URLs and descriptions)

Protect QR code and image endpoints from abuse

🧩 Development Phases

Phase 1 – MVP Launch

Google login

Card creation form

QR Code generation

Mini site preview page

Phase 2 – Dashboard & Stats

Dashboard with saved cards

View/edit/delete cards

Add analytics (click/view tracking)

Phase 3 – Sharing Tools & Polish

WhatsApp/web share integration

Export QR Code to PNG/PDF

Weekly email report (basic stats)

🚧 Challenges & Risks

Supabase Row Level Security config

Ensuring QR Codes remain valid with custom links

Performance optimization for mobile users

Supporting image uploads with proper CDN delivery

🚀 Future Expansions

Subscription tiers (freemium model)

Custom domains for cards

Templates marketplace (for design presets)

AI suggestions for card text or images

Team accounts for agencies creating cards for clients

# Project Overview – Micro SaaS: Confirmação Simplificada de Presença

## 🎯 Objective

Develop a lightweight and functional SaaS for managing invitations and RSVP confirmations for personal and corporate events.  
The tool allows users to:

- Create events  
- Send personalized invitations via WhatsApp or email  
- Monitor confirmations in real-time through an intuitive dashboard  

---

## 🛠️ Tech Stack

- **Next.js** – App Router frontend hosted on Vercel  
- **TailwindCSS 4** – Clean, responsive UI  
- **Supabase** – Authentication, database, file storage  
- **Twilio Sandbox (WhatsApp)** – Sending invitations with unique RSVP links  
- **EmailJS / Resend (optional)** – Email alternative  
- **html2pdf.js** – Export attendance reports as PDF  

---

## 📌 Key Features

### 1. Event Creation & Management

- Enter event name, date/time, location (with optional Google Maps link), type, and a personalized message  
- Each event has a unique access link and code  

### 2. Personalized Invitations

- Import or manually enter guest list (name + contact)  
- Generate unique confirmation links for each guest  
- Send invitations via WhatsApp (Twilio) or optionally via email  
- Include "Yes, I'm going" confirmation button in the message  

### 3. One-Click RSVP Confirmation

- Guest receives event details and a confirmation button  
- Optional guest message (e.g., “bringing a plus-one”)  
- RSVP is saved in real time  
- Confirmation page may include QR code for check-in  

### 4. Organizer Dashboard

- Display of total, confirmed ✅, pending ⏳, and declined ❌ guests  
- Filter guests by status or name  
- Visual statistics and charts  
- Send automatic reminders to pending guests  

### 5. Reports and Exports

- Export RSVP data as PDF or CSV  
- Shareable read-only public report link  
- Final reports include attendance rate and guest interaction history  

---

## 🔐 Authentication and Profiles

- Login via email or Google (Supabase Auth)  
- Each user accesses only their events  
- Roadmap includes team mode for multi-user events  

---

## 💡 Competitive Differentiators

- Clean and intuitive interface for non-technical users  
- Confirm presence with a single click  
- No app installation required  
- Replaces manual spreadsheet workflows  

---

## 👥 Target Audience

| Segment                 | Example Use Cases                        |
|------------------------|------------------------------------------|
| Social Events           | Birthdays, weddings, baptisms            |
| Small Businesses        | Product launches, meetups, internal events|
| Corporate Events (Simple)| Workshops, happy hours, team offsites    |
| Independent Organizers  | Open classes, community events, sports   |

---

## 🚀 Development Roadmap (Initial)

- [ ] Create project using Cursor + TailwindCSS 4  
- [ ] Set up Supabase tables  
- [ ] Build event creation form  
- [ ] Integrate Twilio API (Sandbox)  
- [ ] Create RSVP confirmation page  
- [ ] Build dashboard with filters and graphs  
- [ ] Add export functionality (PDF/CSV)  

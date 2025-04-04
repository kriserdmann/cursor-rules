# App Flow, Pages & User Roles – Digital Card & Mini Site Creator

## 🧭 Core Pages

### 1. `/` – Home / Landing Page
- Intro to the product
- CTA: Login with Google

### 2. `/dashboard`
- List of created cards
- Button: "Create New Card"
- Edit / Delete / Share (QR) actions per card

### 3. `/create`
- Full customization form
- Upload image, enter business name, description, links
- Color & font selection
- Toggle payment option
- Save button → Generates unique link and QR code

### 4. `/preview/[slug]`
- Public-facing mini site card
- Displays all user-entered info
- Mobile-optimized

### 5. `/api/generate-qr`
- Serverless function to generate and return QR code image

### 6. `/api/track-visit`
- Logs card views or button clicks

---

## 👥 User Roles

### 1. **Authenticated User (default)**
- Create and manage their own cards
- Generate QR codes
- Access dashboard and stats

### 2. **Public Viewer (no login)**
- Can view any shared card via slug URL
- No access to dashboard or edit functions

---

## 🔄 User Flow
1. User signs in via Google
2. Lands on dashboard → sees cards or empty state
3. Clicks "Create Card" → fills form
4. Sees live preview → saves
5. Gets custom URL and QR code to share
6. Tracks stats optionally in dashboard


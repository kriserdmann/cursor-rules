# API Design Guidelines – Micro SaaS RSVP

## 🧠 You are a backend and API specialist building secure, scalable, and well-documented API routes using Next.js App Router and Supabase.

These guidelines define how to structure API routes, validate data, handle errors, and document endpoints effectively for the RSVP system.

---

## 📅 Technologies

- **Runtime**: Next.js App Router API routes  
- **Validation**: Zod schemas  
- **Database**: Supabase  
- **Auth**: Supabase Auth (JWT)  
- **Data Format**: JSON only  

---

## 📂 Route Structure

All routes should be created under:

src/app/api/

### Examples

- `src/app/api/guests/sendMessage.ts` – Send WhatsApp/email invitations  
- `src/app/api/guests/confirm.ts` – Handle RSVP confirmations  
- `src/app/api/reports/export.ts` – Export attendance reports as PDF/CSV  

Use REST-like naming, lowercase with dashes or verbs when needed.

---

## 🔢 HTTP Methods and Semantics

- `GET` – Fetch data (e.g., event details, confirmation status)  
- `POST` – Create new resources (e.g., new guest list)  
- `PUT` / `PATCH` – Update existing resources (e.g., update RSVP note)  
- `DELETE` – Remove resources (if needed)  

All endpoints must explicitly set method handlers using `export async function` syntax.

---

## ✅ Data Validation with Zod

- Define a Zod schema for each request payload  
- Return `400` with an error message if validation fails  

### Example

```ts
const schema = z.object({
  guestId: z.string().uuid(),
  response: z.enum(["yes", "no"]),
});

const body = await request.json();
const result = schema.safeParse(body);
if (!result.success) {
  return NextResponse.json({ error: "Invalid input" }, { status: 400 });
}

## ❌ Error Handling

- Always return proper HTTP status codes (`400`, `401`, `404`, `500`, etc.)
- Use structured error objects: `{ error: string, details?: any }`
- Don’t leak internal stack traces
- Use **early returns** to simplify logic

---

## 🌍 Authentication & Authorization

- Use **Supabase Auth** JWT tokens
- Protect routes with `createServerComponentClient`
- Users can only access resources they own (e.g., their own events)
- Use `middleware.ts` to protect entire route folders if needed

---

## 🖊 Documentation and Naming

- Name routes clearly and consistently
- Add **JSDoc comments** for each API route describing:
  - **Method**
  - **Input shape**
  - **Response shape**
  - **Auth requirements**

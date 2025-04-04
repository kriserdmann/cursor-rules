# Database Modeling Guidelines – Micro SaaS RSVP

## 🧠 You are a database designer working with PostgreSQL via Supabase.

This document defines best practices for designing and managing the database schema for the RSVP system. It ensures data integrity, performance, scalability, and clear relationships between entities.

---

## 🌐 General Principles

- Use **UUIDs** as primary keys for all tables
- Use **snake_case** for table and column names
- Avoid nullable fields unless strictly necessary
- Separate user-facing labels from internal IDs
- All tables must include:
  - `id` (UUID, PK)
  - `created_at` (timestamp)
  - `updated_at` (timestamp, optional)

---

## 📊 Core Tables

### `events`

| Column      | Type       | Description                        |
|-------------|------------|------------------------------------|
| id          | UUID (PK)  | Unique event ID                    |
| user_id     | UUID (FK)  | Owner of the event (authenticated) |
| title       | Text       | Event name                         |
| description | Text       | Invitation message                 |
| date_time   | Timestamp  | Event date and time                |
| location    | Text       | Address or venue                   |
| created_at  | Timestamp  | Creation date                      |

---

### `guests`

| Column        | Type       | Description                         |
|---------------|------------|-------------------------------------|
| id            | UUID (PK)  | Unique guest ID                     |
| event_id      | UUID (FK)  | Associated event                    |
| name          | Text       | Guest full name                     |
| contact       | Text       | Email or WhatsApp                   |
| confirmed     | Boolean    | Whether they confirmed              |
| responded_at  | Timestamp  | Confirmation timestamp              |
| response_note | Text       | Optional note by the guest          |
| created_at    | Timestamp  | Date added to the list              |

---

## 🏢 Optional Supporting Tables

### `reminders`

| Column    | Type       | Description                          |
|-----------|------------|--------------------------------------|
| id        | UUID (PK)  | Unique reminder ID                   |
| guest_id  | UUID (FK)  | Related guest                        |
| sent_at   | Timestamp  | When reminder was sent               |
| channel   | Text       | Method used ("email" or "whatsapp") |

---

### `event_links`

| Column     | Type       | Description                          |
|------------|------------|--------------------------------------|
| id         | UUID (PK)  | Unique short link ID                 |
| event_id   | UUID (FK)  | Related event                        |
| slug       | Text       | Slug used in URL                     |
| created_at | Timestamp  | Date link was created                |

---

## ✅ Indexing and Performance

- Index all foreign keys (`event_id`, `user_id`, etc.)
- Add indexes to frequently filtered fields (`confirmed`, `responded_at`)
- Avoid joins in large queries – consider materialized views or denormalized summaries

---

## 🚫 Data Integrity

- Use foreign key constraints between tables
- Use `ON DELETE CASCADE` only when safe (e.g., `guests` → `events`)
- Validate phone numbers/emails on insert (server-side or client-side)
- Prevent duplicate contacts per event using composite constraints or unique indexes

---

## 📝 Naming Conventions

- Tables: plural and snake_case → `events`, `event_links`
- Columns: lowercase snake_case → `date_time`, `user_id`
- Enums: lowercase with underscore (if used)

---

## 🔄 Migrations and Changes

- Use Supabase SQL editor or CLI for schema changes
- Always test changes in development before pushing to production
- Keep track of schema versions using Git (optionally in `supabase/migrations`)

---

> Follow this schema to ensure scalable and reliable data storage throughout the lifecycle of this SaaS project.

# ClipLine — Barbershop Appointment Service (Group SE-2621)

Live Web Application & Relational Database System for ICT Assignment 3.

## 🔗 Project Links
- **Figma UI/UX Design (Stage 1 & 2):** [View Figma Board (node-id=4-176)](https://www.figma.com/design/yrTc2frLZ37fe8FxlI36Q5/ICT?node-id=4-176&p=f&t=l3t7K6tnkXCDFj0X-0)
- **Database Engine:** PostgreSQL 18 (Cloud Realtime via Supabase)

## 🛡️ Architecture & Security Highlights
1. **3NF Relational Schema:** 6 normalized tables (`users`, `barbers`, `services`, `appointments`, `appointment_services`, `favorites`).
2. **Double-Booking Prevention:** Enforced at the database engine level via partial unique index `uq_active_barber_start` on `(barber_id, starts_at) WHERE status = 'confirmed'`.
3. **Cryptographic Authentication:** Passwords hashed via `PBKDF2-HMAC-SHA256` with 210,000 iterations and unique salts.
4. **SQL Injection Defense:** All database writes use strict parameterized queries.
5. **Kazakhstan Law No. 94-V Compliance:** Enforces strict data minimization (excludes IIN, phone numbers, and credit card storage). 

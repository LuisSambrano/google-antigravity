# Supabase Security & Architecture Standards

## 1. Row Level Security (RLS)

- **Enable by Default**: RLS must be enabled on ALL tables.
- **Policies**:
  - `SELECT`: Public for content, User-only for private data (`auth.uid() = user_id`).
  - `INSERT/UPDATE`: Strictly `auth.uid() = user_id` or Admin role check.

## 2. Auth Implementation

- **SSR Auth**: Use `@supabase/ssr` package. Do NOT use the legacy auth helpers.
- **Middleware**: Protect routes via `middleware.ts`. Redirect to `/login` if no session.

## 3. Database Schema

- **Snake Case**: Tables and columns are `snake_case`.
- **Foreign Keys**: Explicit relationships. Use `On Delete Cascade` carefully.
- **Profile Pattern**: Use a `public.profiles` table linked to `auth.users` via trigger.

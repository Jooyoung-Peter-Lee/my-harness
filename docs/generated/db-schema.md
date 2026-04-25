# DB Schema Reference

> This file is generated (or manually maintained) as a reference for the current database schema.
> Update whenever migrations are applied.
> Last updated: (fill in date)

---

## Tables

> Replace this section with your actual schema. Example format below.

### `users`

| Column | Type | Nullable | Default | Notes |
|---|---|---|---|---|
| `id` | uuid | NO | `gen_random_uuid()` | Primary key |
| `email` | text | NO | — | Unique |
| `created_at` | timestamptz | NO | `now()` | |
| `updated_at` | timestamptz | NO | `now()` | |

---

### `(next table)`

| Column | Type | Nullable | Default | Notes |
|---|---|---|---|---|
| | | | | |

---

## Enums

| Name | Values |
|---|---|
| (e.g., `user_role`) | `admin`, `member`, `viewer` |

---

## Indexes

| Table | Columns | Type | Purpose |
|---|---|---|---|
| (e.g., `users`) | `email` | UNIQUE | Fast email lookup |

---

## Foreign Keys

| From | To | On delete |
|---|---|---|
| (e.g., `posts.user_id`) | `users.id` | CASCADE |

---

## How to regenerate

```bash
# Fill in the command that regenerates this file, e.g.:
# npx prisma generate && npx tsx scripts/dump-schema.ts > docs/generated/db-schema.md
```

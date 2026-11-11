# Results Vault - System Architecture & Security

## What was built
A secure, multi-role school examination system. It features a Teacher Dashboard for viewing and publishing marks, and a Student Portal for viewing results. 

The stack uses Next.js for the frontend, FastAPI for the backend, and Supabase (PostgreSQL) for the database. The system is built with strict JWT authentication, Alembic database migrations, immutable audit logs, and Row Level Security (RLS).

## The 3 Riskiest Things & How They Are Tested

### 1. Data Leakage (Student A viewing Student B's marks)
Risk: A hacker could change the URL from `/results/1` to `/results/2` to steal another student's grades.
How it is tested: 
- Playwright E2E test logs in as Student 1, tampers with the URL, and asserts that the backend returns a `403 Forbidden` error.
- FastAPI checks the `user_id` inside the JWT token.
- Supabase RLS policies ensure the database returns only rows matching the logged-in user.

### 2. Unauthorized Mark Tampering (Students changing their own marks)
Risk: A student could try to hit the teacher's publish endpoint or modify marks directly.
How it is tested:
- FastAPI has a strict RBAC check. It queries the `teachers` table to verify the user is a registered teacher. Students get a `403 Forbidden`.
- Playwright tests verify that a student cannot see their marks if the status is not explicitly set to `Published`.

### 3. Audit Log Deletion (Covering up a mistake)
Risk: A teacher or hacker changes a mark and tries to delete the audit log to hide the evidence.
How it is tested:
- A Postgres Trigger (`trigger_prevent_audit_changes`) is applied to the `mark_changes` table.
- ANY attempt to `UPDATE` or `DELETE` a row automatically throws a database exception (`RAISE EXCEPTION`).
- This makes the logs completely immutable, even for database administrators.

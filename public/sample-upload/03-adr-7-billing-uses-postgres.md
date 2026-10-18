---
title: ADR-7: Billing Service uses Postgres
author: Rhea Patel
date: 2026-09-12
status: accepted
---

# ADR-7: Billing Service uses Postgres

Billing Service moves from SQLite to Postgres. Rhea Patel owns the migration.
Customer Portal reads invoices through Billing Service and needs no change.

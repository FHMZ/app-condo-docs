#### Version: 0.1.0

---

## 🏢 Condo Management - General Technology Standards

#### *This document defines a **standard, company-wide naming convention** for all modules of the Condominium Management system. Each functional module is presented on its own page with a brief description and naming examples.*

---

## 🚀 Projects Naming Structure
> ```
> [platform]-[app-name]-[module]-[domain]-[type]
> ```


## 📌 Segments

### 1. `platform` Defines the technical platform or service layer
  - `api` — Backend services.
  - `web` — Web frontend apps.
  - `mob` — Mobile apps.
  - `bff` — Backend for frontend services.
  - `lib` — Shared libraries (frontend or backend) (domain or cross-cutting).

### 2. `app-name` Global system or context name.
  - `condo-mgmt` — Short for condominium management.

### 3. `module` Specific functional area or business feature.
  - `accounting`
  - `communication`
  - `maintenance`

### 4. `domain` Contextual business unit or entity.
  - `bill`
  - `notification`
  - `meeting`

### 5. `type` Type of artifact.
  - `be` — Backend
  - `fe` — Frontend
  - `lib` — Library
  - `bff` — Back for Frontend

---

## 📁 Applications Technologies and Repository Structures

```BFF Service
repo/
├── api-condo-mgmt-financial-dashboard-bff/
    ├──
```

```Backend Service
repo/
├── api-condo-mgmt-financial-dashboard-be/
    ├──
```

```Library Service
repo/
├── lib-condo-mgmt-financial-dashboard-be/
    ├──
```

```Frontend Web
repo/
├── web-condo-mgmt-financial-dashboard-fe/
    ├──
```

```Frontend Mobile
repo/
├── mob-condo-mgmt-financial-dashboard-fe/
    ├──
```

---

## 🏷️ Repository Versions (GIT)

1. **Semantic Versioning (SemVer):** Use `MAJOR.MINOR.PATCH` with optional pre-release tags (e.g. `-alpha`, `-beta`) and build metadata, e.g. `1.2.3-beta.1`.

2. **Incremental Revision Tags:** For internal drafts or non-release artifacts, adopt revision numbering: `v1.0.0`, `v2.0.0`, or `v1.0.1` for minor edits.

3. **Git Release Tags:** Create annotated Git tags matching your SemVer, e.g.: `git tag -a v1.0.0 -m "Release v1.0.0"`

4. **Repository Naming:** Use lowercase hyphens (no version numbers in the repo name), ex.:

    | **Artifact**       | **Name**                                 |
    |--------------------|------------------------------------------|
    | Backend Service    | `api-condo-mgmt-accounting-bill-be`      |

5. **Environment Suffixes:** Append ex.:

    | **Environment**   | **Suffix**    | **Example Version**   |
    |-------------------|---------------|-----------------------|
    | Development       | `-dev`        | `1.0.0-dev`           |
    | QA                | `-qa`         | `1.0.0-qa`            |
    | Production        | `-prod`       | `1.0.0-prod`          |

6. **Git Branch Naming:**

    | **Branch Type**   | **Format**                            | **Description**               |
    |-------------------|---------------------------------------|-------------------------------|
    | Feature           | `feature/<task-number>_<short-desc>`  | New features                  |
    | Bugfix            | `bugfix/<task-number>_<issue-id>`     | Fixing bugs                   |
    | Hotfix            | `hotfix/<task-number>_<critical-bug>` | Urgent critical bug fixes     |
    | Release           | `release/<version>`                   | Preparing a new release       |

7. **Semantic Versioning:** Append `-v1.0.0` `-v1.0.1` for releases.

8. **Changelog & Release Notes:**
   Maintain a `CHANGELOG.md` following the “Keep a Changelog” format.

---

## 🗄️ Databases

1. **Naming Style:**
   Use lowercase snake_case for schemas, tables, and columns.

2. **Table Names:**
   Prefer plural, descriptive nouns: `tb_invoices`, `tb_user_profiles`.

3. **Primary Keys:**
   Name primary key columns `<table>_id`, e.g. `invoice_id`.

4. **Foreign Keys:**
   Mirror referenced PK names exactly, e.g. `user_id` for `users.user_id`.

5. **Avoid Reserved Words:**
   Don’t use SQL keywords or special characters; stick to letters, numbers, and underscores.

6. **Descriptive, Full Words:**
   Avoid cryptic abbreviations—spell out terms clearly (`customer_address` not `cust_addr`).

7. **Schema Separation:**
   Use schemas or prefixes for grouping (e.g. `dev_`, `prod_`, or domain schemas like `finance`).

8. **Documentation & Diagrams:**
   Keep an up-to-date ERD and store SQL scripts in `db/migrations/` or `db/ddl/`.

---

## 🛠️ CI/CD Pipelines

### ✅ Naming Examples

| **Artifact**            | **Name**                                   |
|-------------------------|--------------------------------------------|
| Backend Service         | `ci-api-accounting-bill-be.yml`            |
| Back for Frontend (BFF) | `ci-api-shared-utils-bff.yml`              |
| Frontend (General)      | `ci-web-communication-notification-fe.yml` |
| Library                 | `ci-lib-shared-utils-fe.yml`               |

---

## 🌟 Additional Standards & Best Practices

1. **Kebab-case:** for all names plural names (services, repos, models, controllers, utils, files).
2. **Docker Image Tags:** `<artifact>:<version>-<env>` (e.g., `api-condo-mgmt-accounting-bill-be:1.0.0-prod`).
3. **API Version Path:** Include version path or header (e.g., `/v1/module/domain`).
4. **Configuration Management:** Use environment variables prefixed by service name (e.g., `ACCOUNTING_DB_URI`).
5. **Documentation:** Maintain `docs/` folder with OpenAPI/Swagger specs, architecture diagrams.

---

## 🔧 Recomended Technologies for `MVP_1_R1`

| **Layer**                     | **Supabase (MVP)**                                                    |
|-------------------------------|-----------------------------------------------------------------------|
| **Mobile**                    | Flutter + `supabase_flutter`                                          |
| **Web Admin**                 | Next.js + TypeScript + `@supabase/supabase-js`                        |
| **Backend / Business Logic**  | Supabase Edge Functions (Deno) + RPC/Triggers on Postgres             |
| **Database**                  | PostgreSQL (via Supabase)                                             |
| **Authentication**            | Supabase Auth (GoTrue)                                                |
| **File Storage**              | Supabase Storage (S3-compatible)                                      |
| **Realtime & WebSockets**     | Supabase Realtime (Postgres replication)                              |
| **Push Notifications**        | Direct integration with FCM (Firebase Cloud Messaging) or OneSignal   |
| **Charts & UI**               | Victory (Flutter) / Recharts (Next.js)                                |
| **CI/CD & Infrastructure**    | GitHub Actions + Supabase CLI                                         |
| **Monitoring & Logs**         | Supabase Studio + potential export to Grafana/Prometheus              |

---

This naming standard, combined with these operational practices, prepares our platform for future growth, automation, and cross-team collaboration.

---

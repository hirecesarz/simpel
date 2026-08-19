# Simpel — Engineering & AI Agent Guidelines

**Document:** `PRD.md`  
**Version:** 1.2
**Author:** Cesar Zanetti
**E-mail**: hirecesarz at outlook dot com
**Product:** Simpel
**Repository:** Simpel Web Application
**Primary Product Source of Truth:** `PRD.md`
**Primary Interface Language:** Brazilian Portuguese
**Code & Documentation Language:** English

---

## 1. Purpose

This document defines the engineering, architecture, security, development, testing, deployment, and AI coding-agent rules for Simpel.

Simpel is a privacy-first Brazilian Talent Acquisition / Recruitment & Selection Micro-SaaS.

The primary engineering objective is:

> **Build the simplest production-ready architecture that can safely support the product defined in `PRD.md`, while keeping the codebase easy for humans and AI coding agents to understand and evolve.**

Optimize for:

**Clarity + Security + Maintainability + Simplicity + Correctness**

Do not optimize for architectural sophistication.

---

# 2. Source-of-Truth Hierarchy

The repository may contain multiple documents with different responsibilities.

## 2.1 `PRD.md`

`PRD.md` is the authoritative source for:

* Product vision
* Product principles
* MVP scope
* User roles
* Product workflows
* Functional requirements
* Business rules
* Acceptance criteria
* Product assumptions
* Product metrics
* Product-level open questions

If implementation conflicts with `PRD.md`, the implementation MUST NOT silently redefine the product requirement.

---

## 2.2 `AGENTS.md`

`AGENTS.md` is authoritative for:

* Engineering conventions
* Repository conventions
* Architecture
* Coding practices
* Testing expectations
* Security engineering rules
* Development workflow
* Deployment constraints
* AI coding-agent behavior

---

## 2.3 `DESIGN.md`

`DESIGN.md` is authoritative for:

* Visual identity
* Design system
* Typography
* Colors
* Spacing
* UI components
* Interaction patterns
* Detailed responsive behavior
* Detailed accessibility guidance

---

## 2.4 `PRIVACY.md`

`PRIVACY.md` is authoritative for:

* Privacy policy
* Personal-data processing disclosures
* Data rights
* Retention policies
* Legal privacy requirements
* Detailed privacy practices

Engineering implementation MUST support the requirements defined there.

---

## 2.5 `TERMS.md`

`TERMS.md` is authoritative for:

* Legal terms
* Contractual conditions
* Platform rules
* Legal responsibilities

Engineering documentation MUST NOT invent legal terms.

---

## 2.6 Conflict Resolution

When documents appear inconsistent:

1. Identify which document owns the decision.
2. Follow the authoritative document for that concern.
3. Do not silently rewrite another document.
4. If implementation cannot proceed safely, document the ambiguity.
5. Ask for clarification when the ambiguity materially affects product behavior, security, privacy, payments, or data integrity.

---

# 3. Technology Baseline

The intended stack is:

* Python 3.14
* Django 5.2
* Tailwind 4.3
* Alpine.js 3.15
* PostgreSQL 18.4
* GitHub
* DigitalOcean Droplet (Ubuntu 24.04 LTS)
* Mercado Pago
* Clicky

## 3.1 Compatibility

The specified Python/Django combination is acceptable.

Django 5.2 supports Python 3.14 starting with Django 5.2.8. Django 5.2 is an LTS release. The project MUST remain on a Django 5.2-compatible release while the 5.2 line is the intentional baseline.

PostgreSQL 18.4 is an appropriate production database target. PostgreSQL recommends using the current minor release for a supported major version.

No technology in the stated stack requires replacement solely for compatibility reasons.

Tailwind and Alpine.js should be used via CDN, no local or npm-based installations.

## 3.2 Version Discipline

The project MUST pin or constrain production dependencies sufficiently to make builds reproducible.

Developers and AI agents MUST NOT perform major-version upgrades as part of unrelated feature work.

Dependency upgrades SHOULD be isolated into focused changes.

Security updates MAY be applied independently when necessary.

---

# 4. Architectural Principles

The following principles apply pragmatically:

* Clean Code
* Clean Architecture
* SOLID
* KISS
* DRY
* YAGNI

They MUST NOT be interpreted as requirements to introduce unnecessary abstraction.

## 4.1 KISS

Prefer the simplest implementation that satisfies:

* Product requirements
* Security requirements
* Data integrity
* Testability
* Maintainability

## 4.2 YAGNI

Do not build:

* Generic frameworks
* Plugin systems
* Multi-provider abstractions
* Complex workflow engines
* Event buses
* Repository layers
* Dependency-injection containers
* Generic CRUD abstractions

unless a concrete current requirement justifies them.

## 4.3 SOLID

Apply SOLID at meaningful boundaries.

Do not create interfaces merely because an interface can exist.

Django's built-in abstractions are sufficient in most cases.

## 4.4 DRY

Do not duplicate stable business rules.

However, two pieces of code that happen to look similar MUST NOT automatically be abstracted if their responsibilities or change patterns differ.

Prefer duplication over premature coupling.

---

# 5. Architectural Style

Simpel SHOULD use a pragmatic Django monolith.

The default architecture is:

> **Modular Django monolith + PostgreSQL + server-rendered HTML + small amounts of JavaScript + isolated external integrations**

Do NOT introduce microservices for MVP.

Do NOT introduce a separate frontend application unless a demonstrated product requirement makes it necessary.

Do NOT introduce asynchronous infrastructure merely because the application may eventually need it.

A modular monolith provides sufficient separation while keeping deployment and operations simple.

---

# 6. Recommended Project Structure

The project SHOULD follow a structure similar to:

```text
simpel/
├── manage.py
├── pyproject.toml
├── README.md
├── AGENTS.md
├── PRD.md
├── DESIGN.md
├── PRIVACY.md
├── TERMS.md
├── .env.example
├── .gitignore
├── .dockerignore
├── Dockerfile
├── nginx/
│   └── simpel.conf
├── systemd/
│   └── simpel.service
├── gunicorn.conf.py
│
├── config/
│   ├── __init__.py
│   ├── asgi.py
│   ├── wsgi.py
│   ├── urls.py
│   └── settings/
│       ├── __init__.py
│       ├── base.py
│       ├── dev.py
│       └── prd.py
│
├── apps/
│   ├── accounts/
│   ├── companies/
│   ├── vacancies/
│   ├── applications/
│   ├── subscriptions/
│   └── core/
│
├── integrations/
│   ├── mercado_pago/
│   ├── google/
│   └── clicky/
│
├── templates/
│   ├── base.html
│   ├── components/
│   └── ...
│
├── static/
│   ├── css/
│   ├── js/
│   └── images/
│
├── tests/
│   ├── integration/
│   ├── security/
│   └── ...
│
└── docs/
    └── ...
```

This is a guideline rather than an absolute requirement.

The actual repository structure MUST remain understandable and SHOULD evolve only when growth justifies it.

---

# 7. Django Application Boundaries

Do not create one Django app for every noun in the product.

Apps SHOULD represent cohesive business capabilities.

The initial boundaries SHOULD be:

## `accounts`

Responsible for:

* User identity
* Authentication
* User roles
* Sessions
* Candidate authentication
* Recruiter authentication
* User-level account behavior

It MUST NOT own vacancy or application business logic.

---

## `companies`

Responsible for:

* Company identity
* Recruiter/company relationship
* Corporate-domain information
* Company-level information required by the product

A company is not automatically considered fully verified merely because its domain is accepted.

---

## `vacancies`

Responsible for:

* Vacancy creation
* Vacancy editing
* Vacancy publication
* Vacancy closure
* Vacancy state
* Vacancy ownership
* Vacancy discovery
* Vacancy filtering
* Vacancy visibility

The three MVP vacancy states are:

* Draft
* Published
* Closed

Do not introduce additional states without a concrete requirement.

---

## `applications`

Responsible for:

* Candidate applications
* Selection processes
* Application ownership
* Application state
* Selection-stage transitions
* Candidate withdrawal
* Recruiter Candidate management

The MVP SHOULD use the predefined selection stages from the PRD rather than a configurable workflow engine.

---

## `subscriptions`

Responsible for:

* Candidate subscription state
* Subscription entitlement
* Premium access decisions
* Payment-provider synchronization at the domain boundary

It MUST NOT contain Mercado Pago-specific HTTP implementation details.

---

## `core`

Only genuinely cross-cutting functionality belongs here.

Examples:

* Shared base model utilities
* Common constants
* Common infrastructure helpers
* Health checks
* Small framework-level utilities

`core` MUST NOT become a dumping ground for unrelated business logic.

---

# 8. Business Logic Placement

A developer or AI agent MUST choose the simplest appropriate location.

## 8.1 Models

Models SHOULD contain:

* Data representation
* Relationships
* Database constraints
* Small invariant-preserving methods
* Behavior tightly coupled to one model

Models SHOULD NOT become large procedural services.

---

## 8.2 Forms

Forms SHOULD contain:

* Input validation
* Presentation-oriented validation
* Field normalization
* User-input-specific validation

Forms SHOULD NOT become the primary location for reusable domain rules.

If a rule must also apply to APIs, management commands, webhooks, or other entry points, it SHOULD live outside the form.

---

## 8.3 Views

Views SHOULD:

1. Authenticate the request.
2. Authorize access.
3. Parse/validate input.
4. Invoke the appropriate business operation.
5. Return the response.

Views SHOULD remain thin.

Views MUST NOT contain large business workflows.

---

## 8.4 Services / Use Cases

A service/use-case function or class SHOULD be introduced when an operation:

* Represents a meaningful business action;
* Coordinates multiple models;
* Requires a transaction;
* Has multiple entry points;
* Requires isolated testing;
* Integrates with an external system;
* Contains enough logic that placing it in a view/model would reduce clarity.

Examples:

```text
publish_vacancy()
apply_to_vacancy()
change_application_stage()
withdraw_application()
activate_subscription()
synchronize_subscription()
```

Do not create a service for:

```text
get_vacancy()
```

merely to move one ORM call out of a view.

---

## 8.5 Selectors / Query Logic

A dedicated query/selector abstraction MAY be used when query logic:

* Is reused;
* Is complex;
* Encodes meaningful read-side business rules;
* Requires optimized query composition;
* Improves testability or readability.

Simple ORM queries SHOULD remain in the relevant view/service/module.

---

# 9. Transactions

Operations that must succeed or fail atomically MUST use database transactions.

Examples include:

* Creating an application while enforcing application uniqueness;
* Moving a Candidate through a selection stage when multiple records must change;
* Activating subscription entitlement based on a confirmed payment event;
* Processing state transitions involving multiple related records.

Use Django's transaction support.

Do not use transactions indiscriminately around every database read.

---

# 10. Authentication

Authentication answers:

> "Who is this user?"

Authorization answers:

> "What may this authenticated user do?"

These concerns MUST remain distinct.

---

## 10.1 Custom User Model

Simpel SHOULD use a custom Django user model from the beginning.

The user model SHOULD provide a stable identity independent of a specific authentication provider.

At minimum, the design must support:

* Candidate
* Recruiter

The role model MUST remain simple.

Do not create complex enterprise RBAC for MVP.

---

## 10.2 Candidate Authentication

Candidates authenticate through Google in the MVP.

Google-specific implementation details MUST remain isolated from the domain model.

The application SHOULD store only the provider identity information necessary to maintain authentication and account integrity.

---

## 10.3 Recruiter Authentication

Recruiters MUST use an eligible corporate email.

Corporate-domain validation and email ownership verification are separate checks.

Passing both checks MUST NOT be treated as complete company verification.

---

# 11. Authorization

Authorization MUST always be enforced server-side.

Frontend visibility is not authorization.

A hidden button is not a permission check.

URL obscurity is not authorization.

Client-provided identifiers MUST never be trusted without authorization checks.

---

## 11.1 Recruiter Ownership

A Recruiter may manage only vacancies they own or are explicitly authorized to manage.

Every protected vacancy operation MUST enforce ownership.

---

## 11.2 Candidate Access

A Candidate may access only:

* Their own profile;
* Their own applications;
* Their own subscription information;
* Selection processes associated with their own applications.

---

## 11.3 Recruiter Candidate Visibility

Recruiters access Candidate information when the Candidate is legitimately associated with a vacancy the Recruiter is authorized to manage.

Recruiters receive unrestricted access to the Candidate database.

---

## 11.4 Object-Level Authorization

Every object-level protected operation MUST verify the relationship between:

```text
current user
    ↓
authorized role
    ↓
target object
    ↓
allowed relationship
```

Never rely solely on:

```text
object_id = requested_id
```

---

# 12. Privacy-First Engineering

Privacy is an architectural requirement.

The system MUST follow data minimization.

Only collect personal data required to:

* Operate accounts;
* Publish and manage vacancies;
* Facilitate applications;
* Manage selection processes;
* Process subscriptions;
* Protect the platform;
* Meet applicable operational/legal requirements.

---

## 12.1 Candidate Data

Candidate profile fields SHOULD be introduced only when there is a clear product purpose.

A field MUST NOT become mandatory simply because it is common in professional profiles.

---

## 12.2 Résumé Files

The MVP does not require résumé uploads.

The application MUST NOT introduce résumé storage, parsing, or file-processing infrastructure without an explicit product decision.

---

## 12.3 Sensitive Data

Avoid collecting sensitive personal data unless a concrete requirement justifies it.

Sensitive data MUST receive additional security consideration.

---

## 12.4 Data Visibility

Personal data MUST be exposed only to authorized users.

Do not serialize entire model objects into templates or responses when only a subset of fields is required.

Prefer explicit field selection.

---

# 13. Privacy & Logging

Logs MUST NOT contain:

* Passwords
* OAuth access tokens
* OAuth refresh tokens
* API keys
* Webhook secrets
* Database credentials
* Django `SECRET_KEY`
* Payment credentials
* Full payment payloads when unnecessary
* Unnecessary Candidate personal data
* Sensitive profile information

Identifiers MAY be logged when operationally useful, provided they do not expose unnecessary personal information.

Prefer internal IDs or non-sensitive references over full personal data.

---

# 14. Secrets Management

Secrets MUST NEVER be committed to Git.

This includes:

* `SECRET_KEY`
* Database credentials
* Mercado Pago credentials
* Google OAuth secrets
* Webhook secrets
* API keys
* Encryption keys
* Production credentials

---

## 14.1 Local Development

Local secrets SHOULD be provided through environment variables.

A local `.env` file MAY be used.

`.env` MUST be ignored by Git.

Provide `.env.example` containing variable names and safe placeholder values only.

Example:

```text
DJANGO_SECRET_KEY=
DATABASE_URL=
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
MERCADOPAGO_ACCESS_TOKEN=
MERCADOPAGO_WEBHOOK_SECRET=
CLICKY_SITE_ID=
```

Never place real values in `.env.example`.

---

## 14.2 Production

Production secrets MUST be stored in environment variables or a restricted server-side secrets mechanism.

They MUST NOT be stored in:

* Docker images
* source code
* committed environment files

Production values should be provided through a restricted `.env` file or equivalent mechanism on the Droplet, with appropriate file permissions. Secret values must never be printed to logs.

---

## 14.3 Secret Scanning

The repository SHOULD use automated secret scanning.

At minimum, the project SHOULD enable:

* GitHub secret scanning where available;
* Dependabot/security alerts where appropriate;
* A lightweight pre-commit or CI secret check if practical.

Security tooling must remain proportional to the project.

---

## 14.4 Secret Rotation

If a secret is exposed:

1. Treat it as compromised.
2. Rotate/revoke it immediately.
3. Remove it from the current source tree.
4. Determine whether it exists in Git history.
5. Rotate dependent credentials if necessary.
6. Document the incident appropriately.

Removing the secret from the latest commit alone is insufficient if it remains in Git history.

---

# 15. Django Security Baseline

Production MUST use Django's security mechanisms correctly.

At minimum:

```text
DEBUG = False
```

Production MUST configure:

* `ALLOWED_HOSTS`
* `CSRF_TRUSTED_ORIGINS`
* HTTPS
* Secure cookies
* Appropriate security headers
* Secure session behavior

Django's deployment checklist MUST be treated as a baseline.

---

## 15.1 CSRF

All state-changing browser requests using Django forms MUST use CSRF protection.

Do not disable CSRF protection to make a form or integration work.

External webhook endpoints MUST use an appropriate authentication/signature mechanism instead of relying on browser CSRF tokens.

---

## 15.2 XSS

Use Django's template autoescaping.

Do not mark content as safe unless its safety is established.

User-generated content MUST be treated as untrusted.

Avoid raw HTML rendering from user-controlled data.

---

## 15.3 SQL Injection

Use the Django ORM and parameterized queries.

Raw SQL MAY be used only when justified.

Raw SQL MUST NOT interpolate user input directly.

---

## 15.4 Open Redirects

Redirect targets derived from user input MUST be validated.

Do not create arbitrary redirect endpoints.

---

## 15.5 SSRF

The application MUST NOT fetch arbitrary user-supplied URLs unless there is a concrete product requirement.

If server-side URL fetching is ever required, implement explicit allowlists and network-level protections.

---

## 15.6 Rate Limiting

Rate limiting SHOULD be considered for abuse-prone operations such as:

* Authentication attempts
* Registration
* Application submission
* Password/email verification flows if introduced
* Webhook endpoints where appropriate

Do not introduce a complex distributed rate-limiting system for MVP without evidence that it is necessary.

---

# 16. Passwords and Credentials

If Django-managed passwords are used for any account type:

* Never store plaintext passwords.
* Use Django's password hashing.
* Never log passwords.
* Never expose password hashes through APIs or templates.

Where an authentication provider eliminates password storage, prefer that approach.

---

# 17. Sessions and Cookies

Production cookies SHOULD use:

```text
Secure
HttpOnly
SameSite
```

with values appropriate to the authentication architecture.

Session lifetime MUST be intentional.

Do not unnecessarily create long-lived sessions.

Authentication state MUST NOT be stored in insecure browser storage merely for convenience.

---

# 18. Vacancy Domain Rules

The MVP vacancy lifecycle is:

```text
Draft → Published → Closed
```

## Draft

A Draft:

* Is not publicly discoverable;
* Can be edited by its authorized Recruiter;
* Does not accept applications.

## Published

A Published vacancy:

* Is discoverable according to product visibility rules;
* Can accept eligible applications;
* Can be edited by its authorized Recruiter.

## Closed

A Closed vacancy:

* Is no longer accepting applications;
* Retains existing applications;
* Retains the selection process history.

Do not introduce additional states without a product requirement.

---

# 19. Application Domain Rules

An application belongs to:

* One Candidate
* One vacancy
* One Recruiter's selection process

A Candidate MUST NOT have duplicate active applications for the same vacancy.

This rule SHOULD be enforced at the database level whenever the schema permits it, in addition to application-level validation.

Closing a vacancy MUST NOT delete its existing applications.

---

# 20. Selection Process

The MVP uses a predefined selection process.

Recommended underlying states:

```text
Applied
In Review
Interview
Finalist
Hired
Rejected
Withdrawn
```

The user-facing Brazilian Portuguese labels belong to the presentation layer.

Recruiters control Recruiter-owned selection-stage transitions.

Candidates may:

* View their current status;
* Withdraw where permitted.

Candidates MUST NOT modify Recruiter-controlled selection states.

---

# 21. State Transitions

Business state changes SHOULD be explicit.

Avoid scattered assignments such as:

```python
application.status = "hired"
application.save()
```

when the transition contains meaningful business rules.

Prefer a domain operation such as:

```python
change_application_stage(...)
```

when authorization, validation, timestamps, notifications, audit behavior, or related state changes are involved.

---

# 22. Radar

Radar is an operational workspace, not a generic analytics dashboard.

## Recruiter Radar

It should primarily expose:

```text
Vacancies
    ↓
Candidates
    ↓
Candidate
    ↓
Selection Status
```

## Candidate Radar

It should primarily expose:

```text
Application
    ↓
Selection Process
    ↓
Current Status
    ↓
Next Relevant Action
```

Do not turn Radar into an analytics platform.

---

# 23. Subscription Domain

The subscription domain belongs to Simpel.

Mercado Pago is the payment provider.

Simpel MUST own its own local entitlement state rather than treating the external provider as the application's database.

The application SHOULD maintain enough local state to answer:

> "Does this Candidate currently have premium entitlement?"

without requiring a provider API request on every page view.

---

## 23.1 Subscription States

The implementation MUST support the product's required lifecycle, including states equivalent to:

* Inactive
* Active
* Canceled/pending expiration where applicable
* Expired
* Payment failure where operationally required

Exact internal enum names MAY differ.

---

## 23.2 Entitlement

Premium access MUST be derived from confirmed subscription entitlement.

Do not grant premium access merely because:

* The user clicked "subscribe";
* The payment page opened;
* The frontend reported success;
* A client-side callback claimed success.

---

# 24. Mercado Pago Integration

Mercado Pago-specific code MUST remain isolated under an integration boundary.

Recommended conceptual structure:

```text
integrations/
└── mercado_pago/
    ├── client.py
    ├── webhooks.py
    ├── mapping.py
    └── exceptions.py
```

The exact structure MAY differ.

Core subscription code MUST NOT depend directly on Mercado Pago SDK objects throughout the application.

---

## 24.1 Integration Boundary

Prefer:

```text
Simpel Subscription Domain
        ↓
Mercado Pago Integration
        ↓
Mercado Pago API
```

Avoid:

```text
Views
Models
Templates
Business Logic
Mercado Pago SDK
```

being tightly coupled everywhere.

---

## 24.2 Credentials

Mercado Pago credentials MUST come from environment/production secrets.

They MUST NOT be committed.

Development and production credentials MUST remain separate.

---

## 24.3 Webhooks

Webhook handling MUST:

1. Authenticate/validate the webhook according to Mercado Pago's supported mechanism.
2. Parse the event safely.
3. Validate relevant identifiers.
4. Be idempotent.
5. Update local state only when the event is trustworthy.
6. Return an appropriate HTTP response.
7. Avoid exposing internal details.

Webhook endpoints MUST NOT trust arbitrary request payloads.

---

## 24.4 Idempotency

Webhook processing MUST be safe to repeat.

The implementation SHOULD persist enough information to recognize already-processed events or otherwise make repeated processing harmless.

Do not assume providers deliver each event exactly once.

---

## 24.5 Payment State

A payment page redirect is not proof of payment.

Premium entitlement MUST depend on a reliable confirmed provider state.

---

## 24.6 Provider Failures

If Mercado Pago is unavailable:

* Core non-payment functionality SHOULD continue operating.
* Existing valid subscription state SHOULD remain available according to its known expiration rules.
* New entitlement activation MUST NOT be falsely granted.
* Errors SHOULD be logged without secrets or unnecessary personal data.

---

## 24.7 Provider Abstraction

Do not build a generic payment-provider framework for MVP.

The code SHOULD have a clean boundary around Mercado Pago so a future provider change is possible without rewriting the subscription domain.

That boundary is sufficient.

---

# 25. Clicky Analytics

Clicky is an optional analytics integration.

Analytics MUST NOT be a dependency of core application behavior.

If Clicky fails:

* Authentication must still work.
* Vacancies must still work.
* Applications must still work.
* Radar must still work.
* Subscription functionality must still work.

Analytics instrumentation SHOULD be isolated from business logic.

Do not add analytics events merely because they are technically possible.

Collect only information justified by product validation.

---

# 26. Database Architecture

PostgreSQL is the production source of persistent application data.

Use Django ORM by default.

---

## 26.1 Database Integrity

Important business invariants SHOULD be enforced at the database level whenever practical.

Examples:

* Unique application per Candidate/vacancy;
* Required relationships;
* Non-null constraints;
* Valid state combinations;
* Referential integrity.

Application validation remains necessary for user experience and domain behavior.

---

## 26.2 IDs

Use UUIDs or integer IDs deliberately.

Do not introduce UUIDs solely because they are fashionable.

If public URLs expose object identifiers and enumeration is a meaningful security/privacy concern, UUIDs MAY be preferred.

Regardless of identifier type:

> Authorization MUST never depend on identifier secrecy.

---

## 26.3 Timestamps

Models SHOULD use explicit timestamps where lifecycle tracking matters.

Prefer timezone-aware datetimes.

Production timezone behavior MUST be consistent.

Do not use naive datetime values for business-critical timestamps.

---

## 26.4 Soft Deletion

Soft deletion MUST NOT be the default.

Use it only when there is a concrete requirement for preserving records while hiding them from normal operations.

For MVP, prefer explicit business states such as:

```text
Draft
Published
Closed
```

when those states adequately represent lifecycle.

---

# 27. Migrations

Every schema change MUST use a Django migration.

Do not manually alter production tables.

Migration files MUST be committed with the code that requires them.

Migrations SHOULD be:

* Small
* Reviewable
* Deterministic
* Safe for existing production data

Destructive migrations MUST be treated as high-risk.

---

## 27.1 Safe Migration Practice

For potentially large or destructive changes:

1. Introduce the new structure.
2. Deploy compatible code.
3. Backfill data if necessary.
4. Switch reads/writes.
5. Remove obsolete structures in a later focused change.

Do not combine destructive schema changes with unrelated feature work.

---

# 28. Query Performance

Do not optimize prematurely.

Do prevent obvious performance problems.

Developers SHOULD watch for:

* N+1 queries
* Unbounded querysets
* Missing indexes on frequent filters
* Loading unnecessary columns
* Large unpaginated lists
* Repeated identical queries inside loops

Use:

```python
select_related()
prefetch_related()
```

when appropriate.

Do not add them blindly.

---

# 29. Pagination

User-facing collections SHOULD be paginated when their size can grow without a predictable small upper bound.

Likely candidates include:

* Vacancies
* Candidates
* Applications
* Reports/moderation items

Do not load an entire potentially large collection into memory merely for convenience.

---

# 30. Frontend Architecture

The frontend uses:

* Django templates
* Tailwind 4.3
* Alpine.js 3.15
* Minimal JavaScript

The default frontend architecture is server-rendered HTML.

Do not introduce:

* React
* Vue
* Angular
* Svelte
* An SPA architecture

unless a future product decision explicitly justifies it.

---

# 31. Progressive Enhancement

Prefer:

```text
Server-rendered page
        +
small targeted JavaScript
```

over:

```text
JavaScript application
        +
API-backed page
```

JavaScript SHOULD enhance interactions rather than become a requirement for every basic workflow.

Core functionality SHOULD remain understandable and maintainable through Django's server-side architecture.

---

# 32. Templates

Templates SHOULD use inheritance.

A typical hierarchy is:

```text
base.html
├── public/base.html
├── accounts/base.html
├── recruiter/base.html
└── candidate/base.html
```

The exact hierarchy MAY vary.

Reusable UI pieces SHOULD live in `templates/components/` or the appropriate app-specific template directory.

Avoid massive templates containing:

* Business logic
* Complex conditional workflows
* Database operations
* Authorization decisions

---

# 33. Tailwind

Tailwind SHOULD be used as the primary UI implementation framework.

Prefer Tailwind utilities/components before creating custom CSS.

Custom CSS is appropriate when product design requires it.

Do not introduce a second UI framework without an explicit reason.

Detailed visual rules belong in `DESIGN.md`.

---

# 34. User-Facing Language

All user-facing UI text MUST be Brazilian Portuguese.

All code MUST be written in English.

This includes:

* Python identifiers
* Django model names
* Function names
* Class names
* Variable names
* Comments
* Technical documentation
* Tests
* Prompts
* Commit messages

Brazilian Portuguese belongs primarily in:

* Templates
* Form labels
* Validation messages
* User notifications
* UI copy
* Product-facing content

Do not use artificial literal translations when a natural Brazilian Portuguese term exists.

---

# 35. Forms and Validation

Forms MUST:

* Validate user input;
* Preserve user-entered values where appropriate;
* Provide understandable errors;
* Clearly identify required fields;
* Avoid collecting unnecessary information.

Validation MUST exist at the appropriate layer.

Important business invariants MUST NOT exist only in browser JavaScript.

Client-side validation is an enhancement, not a security boundary.

---

# 36. Accessibility

The application SHOULD provide accessible:

* Labels
* Form controls
* Keyboard interactions
* Focus states
* Error messages
* Status indicators
* Semantic HTML
* Meaningful button text

Do not use color as the only way to communicate state.

Detailed accessibility guidance belongs in `DESIGN.md`.

---

# 37. Error Handling

Errors MUST be handled deliberately.

Do not use broad exception handling such as:

```python
except Exception:
    pass
```

unless there is an explicit and justified reason.

Never silently swallow critical failures.

---

## 37.1 User-Facing Errors

Production users MUST NOT see:

* Stack traces
* SQL statements
* Internal exception details
* Credentials
* Secret values
* Internal infrastructure information

User-facing messages SHOULD explain:

* What happened;
* What the user can do next.

---

## 37.2 Internal Errors

Unexpected failures SHOULD be logged with enough context to diagnose them without exposing sensitive information.

---

# 38. Logging

Logging SHOULD be structured and useful.

Recommended levels:

* `DEBUG` — local development diagnostics
* `INFO` — significant normal application events
* `WARNING` — abnormal but recoverable conditions
* `ERROR` — failed operations requiring attention
* `CRITICAL` — severe application/system failures

Do not log every request manually.

Do not log secrets.

Do not use logs as a replacement for proper state persistence.

---

# 39. Static Files

Static assets MUST be suitable for immutable production deployment.

The production deployment MUST run the appropriate Django static collection process.

Do not store mutable user-generated data in static directories.

---

# 40. Media Files

The MVP explicitly avoids résumé uploads.

If future product requirements introduce user-uploaded files:

* Do not store uploads in the application source tree.
* Do not assume local DigitalOcean Droplet filesystem persistence.
* Define a dedicated storage strategy first.
* Validate file type and size.
* Treat uploaded files as untrusted.
* Define retention and deletion behavior.

Do not add media infrastructure before the product requires it.

---

# 41. Environment Strategy

Simpel has exactly two application environments:

```text
DEV
PRD
```

There is no staging environment.

Do not create an implicit third environment merely through undocumented configuration.

---

# 42. Development Environment

Development occurs on:

* Ubuntu Linux

Developer instructions MUST work on native Ubuntu Linux.

Avoid assuming:

* Bash
* `grep`
* `sed`
* `awk`
* Linux filesystem paths
* Unix-specific shell syntax

Bash or cross-platform Python commands SHOULD be preferred.

---

# 43. Development Configuration

Development SHOULD use:

```text
DEBUG=True
```

when appropriate.

Development configuration MUST NOT be reused automatically in production.

Local development MAY use a local PostgreSQL instance.

If SQLite is used temporarily for isolated experimentation, the application MUST still be tested against PostgreSQL before relying on PostgreSQL-specific behavior in production.

For meaningful schema/database work, PostgreSQL SHOULD be the normal development database.

Developer instructions should use Ubuntu-native shell commands (e.g., `source .venv/bin/activate`).

---

# 44. Production Configuration

Production MUST:

```text
DEBUG=False
```

Production configuration MUST explicitly define:

* Allowed hosts
* CSRF trusted origins
* Database
* Secret key
* Secure cookies
* HTTPS-related settings (behind Nginx reverse proxy)
* Static files
* Logging
* Third-party credentials
* Analytics configuration

Production values MUST come from environment variables or secure secret storage.

---

# 45. Environment Variable Naming

Use clear uppercase names.

Example:

```text
DJANGO_SETTINGS_MODULE
DJANGO_SECRET_KEY
DJANGO_DEBUG
DJANGO_ALLOWED_HOSTS
DJANGO_CSRF_TRUSTED_ORIGINS

DATABASE_URL

GOOGLE_CLIENT_ID
GOOGLE_CLIENT_SECRET

MERCADOPAGO_ACCESS_TOKEN
MERCADOPAGO_WEBHOOK_SECRET

CLICKY_SITE_ID
CLICKY_ENABLED
```

Avoid ambiguous names such as:

```text
KEY
TOKEN
SECRET
URL
```

when their ownership is unclear.

---

# 46. DigitalOcean Deployment

The production runtime is a DigitalOcean Droplet running Ubuntu 24.04 LTS.

The application SHOULD follow a native Python deployment pattern on Ubuntu using systemd, Gunicorn, and Nginx.

---

## 46.1 Production Secrets

Production secrets MUST be stored in environment variables or a restricted server-side secrets mechanism on the Droplet.

They MUST NOT be stored in:

* Docker images
* source code
* committed environment files

Production values should be provided through a restricted `.env` file or equivalent mechanism on the Droplet, with appropriate file permissions. Secret values must never be printed to logs.

---

## 46.2 Migrations

Production migrations MUST be deliberate.

The deployment SHOULD run migrations before switching traffic to the new application version. A common pattern is to execute:

```bash
python manage.py migrate
```

as part of the deployment script before restarting the application service.

Migration failures MUST prevent an unsafe release from becoming the active application version.

---

## 46.3 Health Checks

Production SHOULD expose a lightweight health endpoint.

The health endpoint MUST NOT:

* Require user authentication;
* Expose secrets;
* Perform expensive operations.

It MAY verify basic application readiness.

Do not make health checks depend on external third-party APIs unless there is a concrete reason.

---

## 46.4 HTTPS

Production traffic MUST use HTTPS.

Django's secure cookie and proxy-related configuration MUST be configured correctly for Nginx reverse proxy architecture.

HTTPS termination MAY be handled by Nginx with Let's Encrypt certificates or by a DigitalOcean Load Balancer.

---

## 46.5 Deployment Safety

For significant production changes:

* Review migrations;
* Review authentication/authorization changes;
* Review payment changes;
* Review secrets;
* Run tests;
* Verify health checks;
* Monitor logs after deployment.

Do not bundle unrelated risky changes into the same deployment.

---

# 47. DigitalOcean Storage

Application filesystem storage MUST be treated as ephemeral unless explicitly backed by an appropriate persistent storage mechanism.

Do not rely on local application filesystem persistence for:

* User uploads
* Business data
* Payment records
* Application state

PostgreSQL is the authoritative persistent store for application data.

---

# 48. Deployment Rollbacks

A rollback MUST consider both:

1. Application code
2. Database schema

Never assume that rolling back application code is safe if a migration has already removed or changed required database structures.

Schema changes SHOULD therefore preserve backward compatibility when practical.

---

# 49. GitHub

GitHub is the source-control platform.

The repository MUST NOT contain:

* Secrets
* Production credentials
* Real `.env` files
* Private keys
* Unnecessary personal data
* Production database dumps

---

# 50. `.gitignore`

At minimum, ignore:

```text
.env
.env.*
!.env.example

__pycache__/
*.py[cod]

.venv/
venv/
env/

.pytest_cache/
.mypy_cache/
.ruff_cache/

.coverage
htmlcov/

*.log

.idea/
.vscode/

Thumbs.db
.DS_Store
```

The actual file MAY contain additional appropriate entries.

Do not blindly ignore files required for deployment or source control.

---

# 51. `.dockerignore`

Sensitive and unnecessary local files SHOULD also be excluded from Docker build context.

At minimum consider:

```text
.git/
.env
.venv/
__pycache__/
.pytest_cache/
.mypy_cache/
.ruff_cache/
tests/
```

The exact list depends on the Docker build strategy.

---

# 52. Dependency Management

Before adding a dependency, ask:

1. Can Python standard library solve this?
2. Can Django solve this?
3. Can Tailwind solve this?
4. Can Alpine.js solve this?
5. Is the dependency actually required?
6. Is it maintained?
7. Is its license appropriate?
8. Does it introduce security/supply-chain risk?
9. Does it materially reduce complexity?

An AI agent MUST NOT add a dependency merely to avoid writing a small amount of straightforward code.

---

# 53. Dependency Upgrades

Dependency upgrades SHOULD be isolated.

Do not combine:

```text
feature implementation
+
Django upgrade
+
database driver replacement
+
frontend framework change
```

in one unrelated change.

Security updates MAY be handled urgently when required.

Major dependency upgrades require explicit consideration of:

* Compatibility
* Security
* Migration impact
* Test coverage
* Deployment impact

---

# 54. Python Coding Standards

Use modern Python appropriate to Python 3.14.

Prefer:

* Clear type hints
* Small functions
* Explicit names
* Early returns where useful
* Straightforward control flow
* Standard-library solutions

Avoid:

* Clever metaprogramming
* Excessive decorators
* Deep inheritance
* Unnecessary generic abstractions
* Hidden side effects

---

# 55. Type Hints

Type hints SHOULD be used for:

* Public functions
* Services/use cases
* Integration boundaries
* Complex data structures
* Functions where the return type is not obvious

Do not add type complexity that makes simple code harder to understand.

---

# 56. Naming

Names MUST be in English.

Prefer:

```python
publish_vacancy()
change_application_stage()
activate_subscription()
```

over:

```python
process_data()
handle_thing()
do_action()
```

Names SHOULD describe domain behavior.

Avoid abbreviations unless they are universally understood within the project.

---

# 57. Comments

Comments SHOULD explain **why**, not **what**.

Bad:

```python
# Set status to active
subscription.status = SubscriptionStatus.ACTIVE
```

Better:

```python
# Entitlement is activated only after confirmed provider state.
subscription.status = SubscriptionStatus.ACTIVE
```

Do not leave comments that become false after code changes.

---

# 58. Docstrings

Docstrings SHOULD be used for:

* Public APIs
* Non-obvious services
* Integration boundaries
* Complex domain behavior
* Reusable utilities

Do not add meaningless docstrings to every trivial method.

---

# 59. Exception Design

Use exceptions for exceptional conditions.

Do not use exceptions as ordinary control flow when a simple conditional is clearer.

Domain-specific exceptions MAY be introduced when callers need to distinguish meaningful business failures.

Examples:

```text
VacancyNotPublishable
UnauthorizedVacancyAccess
DuplicateApplication
SubscriptionNotActive
InvalidPaymentEvent
```

Do not create an exception class for every possible branch.

---

# 60. Tests

Tests are required for meaningful behavior changes.

Testing priority:

1. Security
2. Business rules
3. Authorization
4. Payments
5. Critical workflows
6. Data integrity
7. Important UI behavior
8. Low-risk implementation details

Do not waste effort testing Django itself.

---

# 61. Test Categories

The project SHOULD use:

* Unit tests
* Integration tests
* Model tests
* Form tests
* View tests
* Authentication/authorization tests
* Service/use-case tests
* Payment/webhook tests
* Critical journey tests

The exact distribution SHOULD follow the behavior being tested.

---

# 62. Security Tests

Security-sensitive functionality MUST have explicit tests.

Examples:

* Recruiter cannot access another Recruiter's vacancy;
* Recruiter cannot access unrelated Candidates;
* Candidate cannot access another Candidate's application;
* Candidate cannot modify Recruiter-controlled application stage;
* Closed vacancy rejects new applications;
* Premium information is inaccessible without entitlement;
* Payment callback cannot grant access without validation;
* Duplicate active applications are rejected.

---

# 63. Payment Tests

Mercado Pago integration tests MUST cover:

* Successful payment confirmation;
* Failed payment;
* Expiration;
* Cancellation;
* Repeated webhook delivery;
* Invalid webhook;
* Unknown event;
* Provider failure;
* Entitlement synchronization.

Do not make automated tests depend on real production payment activity.

Use provider-supported sandbox/test facilities or mocked integration boundaries.

---

# 64. Critical User Journeys

At minimum, automated coverage SHOULD protect:

### Recruiter

```text
Register
→ Verify email
→ Access Radar
→ Create vacancy
→ Publish vacancy
→ Receive Candidate
→ Change Candidate stage
→ Close vacancy
```

### Candidate

```text
Google authentication
→ Complete profile
→ Discover vacancy
→ View eligible information
→ Apply
→ Open Radar
→ View status
→ Withdraw where allowed
```

### Subscription

```text
Encounter premium content
→ Start subscription
→ Confirm payment
→ Receive entitlement
→ Access premium information
→ Expire/cancel
→ Lose premium access
→ Retain account/application history
```

---

# 65. Test Database Integrity

Tests SHOULD verify important database constraints rather than only testing Python validation.

If uniqueness or integrity matters in production, the database constraint SHOULD be tested.

---

# 66. Code Quality Checks

The repository SHOULD use lightweight automated quality checks appropriate to the project.

A practical baseline MAY include:

* Formatter
* Linter
* Test suite
* Django system checks
* Dependency/security checks
* Secret scanning

Do not introduce a large quality platform when simple tooling is sufficient.

---

# 67. Django Checks

Before a meaningful change is considered complete, run appropriate Django validation.

At minimum:

```text
python manage.py check
```

Production-related configuration SHOULD also be checked with:

```text
python manage.py check --deploy
```

when validating deployment configuration.

---

# 68. Linux Commands

Documentation SHOULD prefer Ubuntu-native commands.

Examples:

```bash
python -m venv .venv
source .venv/bin/activate
python manage.py runserver
python manage.py test
python manage.py check
```

Production-only commands should use native Ubuntu or DigitalOcean tooling where appropriate.

---

# 69. Git Workflow

Use a simple Git workflow suitable for a Micro-SaaS.

Recommended branches:

```text
main
feature/<short-description>
fix/<short-description>
chore/<short-description>
security/<short-description>
```

Do not create elaborate GitFlow structures.

---

# 70. Conventional Commits

Commits MUST follow Conventional Commits.

Format:

```text
<type>(<scope>): <description>
```

Examples:

```text
feat(vacancies): add vacancy publication workflow
feat(applications): add candidate stage transitions
fix(accounts): prevent consumer email registration
fix(subscriptions): handle repeated payment webhook
security(auth): enforce recruiter vacancy ownership
test(applications): cover duplicate application rule
refactor(core): simplify shared validation
docs(agents): clarify AI agent workflow
chore(deps): update security dependencies
```

Allowed common types:

* `feat`
* `fix`
* `security`
* `refactor`
* `test`
* `docs`
* `chore`
* `perf`
* `build`
* `ci`

---

# 71. Commit Rules

Commits SHOULD:

* Represent one coherent change;
* Be easy to review;
* Avoid unrelated refactoring;
* Explain the actual change;
* Preserve a useful project history.

Avoid:

```text
update
changes
stuff
fix
work
misc
```

Prefer:

```text
fix(applications): prevent duplicate active applications
```

---

# 72. Pull Requests

Pull requests SHOULD contain:

* What changed
* Why it changed
* Relevant product requirement
* Security considerations where applicable
* Migration information
* Test results
* Deployment considerations

Keep pull requests focused.

Do not use a feature PR as an excuse for broad unrelated refactoring.

---

# 73. Code Review

Reviewers SHOULD prioritize:

1. Correctness
2. Security
3. Authorization
4. Data integrity
5. Privacy
6. Business-rule compliance
7. Maintainability
8. Performance
9. Style

Do not block a useful change solely because an alternative implementation is more elegant when the current implementation is safe and maintainable.

---

# 74. AI Coding Agent Rules

AI coding agents are first-class contributors to this repository.

Agents MUST behave conservatively.

---

## 74.1 Before Editing

An AI agent MUST:

1. Read `AGENTS.md`.
2. Read the relevant part of `PRD.md`.
3. Read the relevant part of `DESIGN.md`.
4. Inspect the existing implementation.
5. Identify related tests.
6. Understand existing conventions.
7. Determine whether the requested change belongs in the current architecture.

Do not start editing solely from a user prompt without inspecting the relevant code.

---

## 74.2 Product Source of Truth

Agents MUST treat `PRD.md` as authoritative for product behavior.

Agents MUST NOT silently change:

* Business rules
* User roles
* Subscription entitlement
* Selection stages
* Privacy requirements
* MVP scope
* Acceptance criteria

---

## 74.3 Ambiguous Requirements

When a requirement is ambiguous:

1. Check `PRD.md`.
2. Check relevant documentation.
3. Inspect existing implementation.
4. Prefer the smallest solution consistent with the documented behavior.
5. If ambiguity materially affects product behavior, security, payments, or data integrity, flag it.

Agents MUST NOT invent major product behavior silently.

---

# 75. AI Agent Scope Control

Agents MUST keep changes focused.

An agent working on:

```text
vacancy publication
```

SHOULD NOT also:

* Reformat the entire repository;
* Rename unrelated modules;
* Upgrade Django;
* Replace the authentication library;
* Refactor all models;
* Introduce a new frontend framework.

unless explicitly requested or required to safely complete the task.

---

# 76. AI Agent Dependency Rule

AI agents MUST NOT add a dependency without justification.

Before adding one, the agent SHOULD explain:

* Why existing tools are insufficient;
* What capability the dependency provides;
* Why the dependency is proportionate;
* Any meaningful maintenance/security implications.

---

# 77. AI Agent Security Rule

AI agents MUST NEVER:

* Hardcode secrets;
* Commit credentials;
* Print secret values;
* Copy production credentials into tests;
* Disable security controls merely to make tests pass;
* Bypass authorization;
* Trust client-side permission checks;
* Disable CSRF without a justified architecture;
* Expose personal data for debugging.

---

# 78. AI Agent Testing Rule

For meaningful behavior changes, agents SHOULD add or update tests.

At minimum, test:

* New business rules;
* Changed authorization;
* Changed payment behavior;
* Changed subscription entitlement;
* Changed application lifecycle;
* Changed database constraints.

Agents SHOULD run the narrowest relevant tests first and then broader validation when practical.

---

# 79. AI Agent Documentation Rule

If a code change changes:

* Architecture
* Environment variables
* Deployment behavior
* Security behavior
* Integration behavior
* Important developer workflow

the relevant documentation MUST be updated.

Do not duplicate product requirements from `PRD.md` unnecessarily.

---

# 80. AI Agent Completion Criteria

An AI agent MUST NOT claim a task is complete merely because code was written.

Before finishing, the agent SHOULD verify:

```text
Requirements understood
        ↓
Implementation complete
        ↓
Tests updated
        ↓
Relevant tests executed
        ↓
Django checks executed
        ↓
Security implications reviewed
        ↓
Documentation updated if necessary
        ↓
Diff reviewed
```

If a validation step could not be executed, the agent MUST state that clearly.

---

# 81. AI Agent Architectural Changes

Significant architectural changes require explicit justification.

Examples:

* New Django app
* New external dependency
* New infrastructure component
* New database subsystem
* New authentication mechanism
* New asynchronous worker
* New caching layer
* New frontend framework
* New payment abstraction

The agent SHOULD explain:

* Problem
* Existing limitation
* Proposed solution
* Simpler alternatives considered
* Operational impact

---

# 82. Background Processing

The MVP MUST NOT introduce Celery, Redis, or another queue solely because asynchronous processing is common in SaaS applications.

Background processing MAY be introduced when a concrete requirement emerges, such as:

* Long-running external integration;
* Reliable asynchronous notifications;
* Scheduled product operations;
* Work that cannot safely occur within a request.

Until then, synchronous Django operations are preferred.

---

# 83. Caching

Caching MUST NOT be introduced prematurely.

Before caching, establish:

1. The performance problem;
2. The expensive operation;
3. The expected improvement;
4. Cache invalidation behavior;
5. Failure behavior.

Do not cache subscription entitlement or authorization state in a way that can produce stale security decisions.

---

# 84. Performance Baseline

Performance work SHOULD prioritize:

* Database query efficiency;
* Pagination;
* Correct indexing;
* Avoiding N+1 queries;
* Efficient template rendering;
* Reasonable static assets;
* Small response payloads.

Do not introduce:

* Distributed caches;
* Message queues;
* Search clusters;
* Specialized databases

without evidence, they are necessary.

---

# 85. Search and Filters

The PRD calls for sophisticated vacancy filtering ("Filtros Mágicos para Candidatos").

The PRD also calls for sophisticated candidates filtering ("Filtros Mágicos para Recrutadores").

For MVP, implement the search/filtering capability using PostgreSQL and Django ORM unless measured requirements justify a dedicated search engine.

Do not introduce Elasticsearch, OpenSearch, or another search service merely because the product calls the filters "sophisticated."

The search implementation MUST remain maintainable.

---

# 86. Data Ownership

Every protected object MUST have an understandable ownership or access relationship.

Examples:

```text
Vacancy → Recruiter/company
Application → Candidate + vacancy
Subscription → Candidate
Candidate profile → Candidate
```

If an object's access relationship is unclear, the model design SHOULD be reconsidered before implementation.

---

# 88. Auditability

The MVP does not require a comprehensive enterprise audit-log platform.

However, security- and payment-sensitive state changes SHOULD preserve enough information to investigate important incidents.

Examples include:

* Subscription status changes;
* Payment synchronization;
* Application stage transitions where operationally useful.

Do not log unnecessary personal data merely for hypothetical future auditing.

---

# 89. Notifications

The MVP does not require a complex notification platform.

If notifications are introduced, implement the smallest mechanism required.

Do not introduce:

* Generic notification buses;
* Template engines;
* Campaign infrastructure;
* Multi-channel orchestration

unless the product requires them.

---

# 90. API Architecture

The MVP is primarily server-rendered.

Do not build a public API merely for architectural purity.

If an API becomes necessary for a concrete feature:

* Define explicit authentication;
* Define authorization;
* Validate inputs;
* Limit returned fields;
* Document the contract;
* Test security boundaries.

Internal AJAX/JSON endpoints MAY be introduced selectively.

---

# 91. Database Backups

Production database backups MUST be considered part of operational reliability.

The chosen PostgreSQL hosting arrangement MUST provide an appropriate backup/recovery strategy.

Do not assume that application deployment or Git history is a database backup.

Recovery procedures SHOULD be documented when production operations mature.

---

# 92. Production Data Safety

Production data MUST NOT be copied into development casually.

If production data is required for debugging:

* Minimize the data;
* Remove unnecessary personal information;
* Prefer synthetic or anonymized data;
* Protect any temporary dataset;
* Delete it when no longer needed.

Never commit production database dumps.

---

# 93. Privacy-Safe Debugging

When investigating an issue involving Candidates or Recruiters:

Prefer:

```text
internal object ID
status
timestamp
operation
error category
```

over:

```text
full name
email
profile contents
personal information
```

Only expose personal data when necessary for the specific investigation.

---

# 94. Product Scope Discipline

The MVP is intentionally narrow.

Do not introduce functionality resembling:

* Enterprise ATS systems;
* Professional social networks;
* Complex HRIS platforms;
* AI recruitment ranking;
* Custom recruitment workflow engines;
* Advanced analytics platforms.

A feature must have a clear MVP justification.

---

# 95. Open Questions and Assumptions

The PRD intentionally leaves some implementation/product decisions open.

The following MUST NOT be silently invented:

* Exact subscription price;
* Exact premium vacancy fields;
* Final Candidate visibility matrix;
* Final corporate-domain blocklist strategy;
* Final moderation workflow;
* Final detailed accessibility specification;
* Detailed privacy retention periods;
* Legal requirements not defined by product/legal documentation.

If implementation requires one of these decisions, document the assumption and request clarification when the decision materially affects architecture.

---

# 96. Known Architectural Decisions

The following decisions are intentionally established:

### AD-001 — Monolith

Use a modular Django monolith.

### AD-002 — Database

Use PostgreSQL as the production database.

### AD-003 — Frontend

Use Django templates + Tailwind + Alpine.js + minimal JavaScript.

### AD-004 — Authentication

Candidates use Google authentication.

Recruiters require eligible corporate email plus email ownership verification.

### AD-005 — Applications

Use a simple predefined selection pipeline.

### AD-006 — Payments

Mercado Pago is the payment provider.

Simpel owns local subscription entitlement state.

### AD-007 — Analytics

Clicky is non-critical analytics infrastructure.

### AD-008 — Deployment

DigitalOcean Droplet (Ubuntu 24.04 LTS) is the production platform.

### AD-009 — Environments

Only DEV and PRD exist.

### AD-010 — File Uploads

Résumé uploads are out of scope for MVP.

---

# 97. Technical Review — Resolved Risks

The architecture has been reviewed against the PRD and the stated stack.

## 97.1 Django/Python Compatibility

Django 5.2 supports Python 3.14 from Django 5.2.8 onward. The project version `5.2.17` therefore fits the stated Python 3.14 baseline.

## 97.2 PostgreSQL Version

PostgreSQL 18.4 is a supported PostgreSQL 18 minor release and is an appropriate production target.

The project SHOULD continue following PostgreSQL's current-minor-release practice rather than remaining indefinitely on 18.4.

## 97.3 Two-Environment Constraint

The lack of staging increases deployment risk.

The architecture therefore emphasizes:

* Automated tests;
* Migration safety;
* Production-like PostgreSQL development;
* Small deployments;
* Health checks;
* Focused pull requests;
* Rollback awareness.

Do not create a fake staging environment in application code.

## 97.4 Payment Risk

Payment confirmation is treated as an external event rather than a trusted frontend action.

Webhook validation, idempotency, and local entitlement state are mandatory architectural concerns.

## 97.5 Authorization Risk

Because Recruiters manage Candidate data, object-level authorization is treated as a first-class requirement.

The system MUST never rely on frontend visibility to protect Candidate data.

## 97.6 Privacy Risk

The no-résumé-upload model is preserved because it reduces unnecessary file storage and processing.

## 97.7 Over-Engineering Risk

No microservices, message queues, search clusters, frontend frameworks, generic payment abstraction, enterprise RBAC, or complex ATS workflow engine is required for MVP.

---

# 98. Rules That Belong Outside `AGENTS.md`

The following SHOULD NOT become duplicated in this document:

* Detailed product requirements → `PRD.md`
* Detailed visual design → `DESIGN.md`
* Legal requirements → `TERMS.md`
* Detailed privacy policy → `PRIVACY.md`
* Full deployment tutorial → dedicated deployment documentation
* Full provider API documentation → integration documentation
* Product analytics specification → dedicated analytics documentation when needed

`AGENTS.md` defines engineering constraints, not every detail of the product.

---

# 99. Definition of Done

A meaningful implementation change is considered complete when:

* The requested behavior is implemented;
* Existing product requirements remain intact;
* Authorization is correct;
* Privacy implications are considered;
* Database integrity is preserved;
* Relevant tests exist;
* Relevant tests pass;
* Django checks pass;
* No secrets are introduced;
* No unnecessary dependency is introduced;
* No unrelated refactoring is included;
* Documentation is updated when necessary;
* The resulting architecture remains simpler than the problem requires.

---

# 100. Final Engineering Principle

Every architectural decision should answer:

> **What is the simplest safe solution that solves the current Simpel requirement without making the next change unnecessarily difficult?**

When two solutions are functionally equivalent, prefer the one with:

* Fewer moving parts;
* Fewer dependencies;
* Fewer abstractions;
* Fewer deployment concerns;
* Clearer ownership;
* Easier testing;
* Smaller security surface;
* Easier understanding for AI coding agents.

Simpel should remain a **small, coherent, production-ready Django application**.

Do not build the architecture for the company Simpel might become.

Build the architecture that safely and clearly supports the product Simpel is today.

> **Clarity + Security + Maintainability + Simplicity + Correctness.**

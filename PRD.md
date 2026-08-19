# Simpel — Product Requirements Document

**Document:** `PRD.md`  
**Version:** 1.2
**Author:** Cesar Zanetti
**E-mail**: hirecesarz at outlook dot com
**Product:** Simpel  
**Domain:** `simpelvagas.com`  
**Market:** Brazil  
**Primary Interface Language:** Brazilian Portuguese
**Code & Documentation Language:** English 
**Status:** MVP Product Definition

---

## 1. Product Overview

Simpel is a web application for the Brazilian Talent Acquisition / Recruitment & Selection market.

The platform serves two primary user groups:

1. **Recruiters / Companies**
2. **Candidates / Job Seekers**

Simpel is designed around a simple proposition:

> **Simpel makes recruitment simpler by making job publishing simpler for Recruiters and job discovery simpler for Candidates.**

The product intentionally avoids the complexity commonly associated with traditional HR systems and recruitment platforms.

Simpel prioritizes:

- Simplicity
- Human interaction
- Trust
- Privacy
- Speed
- Clear information
- Low-friction workflows

The MVP is a two-sided platform in which Recruiters can publish and manage vacancies and Candidates can discover vacancies, participate in selection processes, and manage their recruitment activity.

---

# 2. Vision & Product Principles

## 2.1 Vision

Simpel should become a simpler alternative to traditional recruitment platforms by reducing unnecessary friction for both sides of the hiring process.

The product should make:

- publishing a vacancy straightforward;
- discovering relevant opportunities straightforward;
- understanding a selection process straightforward;
- managing recruitment activity straightforward.

## 2.2 Product Principles

### Simplicity

Every feature should solve a clear user problem without introducing unnecessary configuration or workflow complexity.

### Human-first

The product should communicate that recruitment involves people rather than treating Candidates as records moving through an administrative pipeline.

### Privacy-first

Simpel should collect only the information necessary to operate the product.

### Trust

Because jobseekers must trust the vacancies they encounter, Simpel should establish basic mechanisms to reduce fraudulent or low-quality postings.

### Speed

Core actions should require as few steps as reasonably possible.

### Clarity

Users should understand:

- what is happening;
- what they can do;
- what happens next;
- why information is being requested.

### MVP discipline

Features that do not directly support the core product hypothesis should not enter Version 1 merely because they are common in recruitment software.

---

# 3. Problem Statement

## 3.1 Recruiter Problem

Recruitment tools can become unnecessarily complex.

Recruiters may need to configure extensive workflows, manage large amounts of information, and interact with systems designed more for enterprise HR operations than for straightforward recruitment.

Simpel addresses this by providing a focused environment for:

1. creating a vacancy;
2. publishing it;
3. receiving Candidates;
4. managing Candidates through a simple selection process.

## 3.2 Candidate Problem

Candidates often encounter:

- excessive forms;
- résumé-upload requirements;
- unclear vacancy information;
- fragmented application processes;
- limited visibility into selection-process status.

Simpel addresses this by using a lightweight professional profile instead of requiring résumé uploads and by providing a central place where Candidates can discover and follow opportunities.

## 3.3 Trust Problem

A recruitment marketplace must also address fraudulent or low-quality job postings.

Corporate-email registration can increase the initial trust signal for Recruiters, but it is not sufficient on its own.

Simpel therefore requires a small MVP-level trust and moderation layer.

---

# 4. Target Users / Personas

## 4.1 Recruiter

A professional responsible for publishing vacancies and managing Candidates.

Typical needs:

- publish a vacancy quickly;
- receive relevant Candidates;
- organize Candidates;
- understand selection status;
- move Candidates through the process;
- communicate a trustworthy opportunity.

### Primary goal

Fill vacancies without needing an expensive and/or complex ATS.

---

## 4.2 Candidate

A person looking for employment opportunities and participating in recruitment processes.

Typical needs:

- discover relevant vacancies;
- understand the opportunity;
- maintain a reusable professional profile;
- apply without uploading a résumé;
- track applications;
- understand the current status of selection processes.

### Primary goal

Discover and participate in relevant opportunities with minimal friction.

---

# 5. Value Proposition

## 5.1 Recruiters

**Simple vacancy publishing and candidate management without unnecessary ATS complexity and costs.**

Simpel provides Recruiters with:

- free access;
- straightforward vacancy creation;
- centralized Candidate management;
- a simple selection pipeline;
- a dedicated Radar workspace.

## 5.2 Candidates

**A simpler way to discover and follow job opportunities without résumé uploads.**

Simpel provides Candidates with:

- a lightweight professional profile;
- centralized vacancy discovery;
- participation tracking;
- a Radar workspace;
- optional paid access to additional job-opportunity value.

---

# 6. Business Model

## 6.1 Recruiters

Recruiter access is free for the MVP.

Recruiters are not required to purchase a subscription to publish vacancies or manage Candidates.

## 6.2 Candidates

Candidates have access to a paid subscription.

The current business hypothesis is that Candidates pay for:

- early access to job information;
- expanded job details.

This is the primary monetization hypothesis to validate.

## 6.3 Business Model Hypothesis

The MVP should test whether Candidates perceive early and expanded access to opportunities as sufficiently valuable to pay a low-cost recurring subscription.

The product should avoid introducing multiple subscription tiers before there is evidence that segmentation is necessary.

---

# 7. MVP Goals

The MVP should validate four core hypotheses.

### Goal 1 — Recruiter adoption

A Recruiter can register, create a vacancy, publish it, and manage Candidates without requiring extensive onboarding.

### Goal 2 — Candidate engagement

A Candidate can register, create a useful professional profile, discover vacancies, and participate in selection processes.

### Goal 3 — Radar value

Users understand Radar as their central workspace for recruitment activity.

### Goal 4 — Candidate monetization

Candidates demonstrate willingness to pay for meaningful additional access to job opportunities.

---

# 8. MVP Scope

## 8.1 In Scope

The MVP includes:

- Recruiter registration;
- Recruiter authentication;
- corporate-email restriction;
- Recruiter vacancy creation;
- vacancy publication;
- vacancy editing;
- vacancy closing;
- Candidate Google authentication;
- Candidate profile;
- vacancy discovery;
- vacancy detail pages;
- Candidate application;
- selection-process management;
- Candidate application status;
- Recruiter Radar;
- Candidate Radar;
- Candidate subscription;
- Mercado Pago integration;
- basic trust signals;
- vacancy reporting;
- basic moderation;
- privacy-conscious data collection.

## 8.2 Explicitly Not Required for MVP

The following are outside the MVP unless required to operate the core workflows:

- advanced recruitment analytics;
- complex reporting;
- enterprise ATS features;
- multiple Recruiter permission levels;
- résumé parsing;
- résumé uploads;
- interview scheduling;
- video interviews;
- automated candidate matching;
- AI candidate ranking;
- complex communication automation;
- extensive integrations;
- advanced company administration;
- customizable recruitment pipelines;
- complex subscription tiers.

---

# 9. User Roles & Permissions

## 9.1 Recruiter

A Recruiter can:

- create an account;
- authenticate;
- create vacancies;
- edit vacancies;
- publish vacancies;
- close vacancies;
- view Candidates associated with their vacancies;
- move Candidates through the selection process;
- view relevant Candidate profile information;
- report or flag relevant activity.

Recruiters must not access Candidates belonging to unrelated vacancies.

## 9.2 Candidate

A Candidate can:

- authenticate through Google;
- create and manage their profile;
- discover vacancies;
- view available vacancy information;
- apply to vacancies;
- view their applications;
- track selection status;
- manage their subscription;
- access subscription-gated vacancy information when entitled.

## 9.3 Platform Administrator

The MVP does not require an administrative platform.

---

# 10. Core User Journeys

## 10.1 Recruiter Journey

1. Recruiter visits Simpel.
2. Recruiter chooses Recruiter registration.
3. Recruiter provides a corporate email.
4. System validates the email domain.
5. Recruiter completes authentication/account creation.
6. Recruiter enters Radar.
7. Recruiter creates a vacancy.
8. Recruiter provides required vacancy information.
9. Recruiter reviews the vacancy.
10. Recruiter publishes the vacancy.
11. Candidates can discover the vacancy according to its visibility rules.
12. Recruiter receives Candidates.
13. Recruiter manages Candidates through the selection stages.
14. Recruiter closes the vacancy when recruitment ends.

---

## 10.2 Candidate Journey

1. Candidate discovers Simpel.
2. Candidate authenticates with Google.
3. Candidate creates or completes their professional profile.
4. Candidate discovers vacancies.
5. Candidate opens a vacancy.
6. Candidate views the information available to their subscription state.
7. Candidate applies.
8. Candidate becomes associated with the selection process.
9. Candidate sees the application in Radar.
10. Recruiter updates the Candidate's status.
11. Candidate sees the updated status in Radar.

---

## 10.3 Subscription Journey

1. Candidate encounters subscription-gated information.
2. Simpel explains the value of the subscription.
3. Candidate chooses to subscribe.
4. Candidate is redirected to or interacts with Mercado Pago.
5. Payment is processed.
6. Simpel receives confirmation.
7. Candidate's subscription becomes active.
8. Gated information becomes available.
9. When the subscription expires or is canceled, gated access is removed according to the subscription rules.

---

# 11. Functional Requirements

## 11.1 Authentication

### FR-001 — Recruiter registration

The system must allow Recruiters to create accounts using a corporate email address.

### FR-002 — Corporate-email restriction

The system must reject known consumer/webmail domains such as Gmail and Outlook for Recruiter registration.

The domain-blocking mechanism must be maintainable.

### FR-003 — Candidate authentication

The system must allow Candidates to register and authenticate using Google authentication.

### FR-004 — Session management

Authenticated users must be able to access their respective Radar and protected account functionality.

---

# 12. Recruiter Experience

## 12.1 Recruiter Registration

Recruiters must provide a corporate email.

The MVP should use email-domain validation as an initial trust mechanism.

### Corporate-email behavior

If the submitted domain is blocked:

- registration must not proceed;
- the user must receive a clear explanation;
- the interface should avoid exposing unnecessary technical details.

### Domain verification

**MVP decision:** Corporate-domain eligibility and email ownership should both be validated.

Corporate-domain eligibility answers:

> "Does this appear to be a company email?"

Email verification answers:

> "Does this person control this email address?"

Neither should be interpreted as complete company verification.

---

# 13. Vacancy Management

## 13.1 Vacancy Creation

A Recruiter must be able to create a vacancy from Radar.

The vacancy creation flow should collect only information required to communicate and manage the opportunity.

### Minimum vacancy information

The MVP should include:

- Job title;
- Company/employer identity;
- Location;
- Work arrangement;
- Employment type;
- Salary information;
- Description (Responsibilities, Requirements etc).

Salary information should be displayed only to the Candidates with an active Subscription.

The exact field-level specification may be refined during UX design without changing the product requirement.

### FR-005 — Create vacancy

A Recruiter must be able to save a vacancy in an unpublished state.

### FR-006 — Publish vacancy

A Recruiter must be able to publish a completed vacancy.

### FR-007 — Edit vacancy

A Recruiter must be able to edit an active vacancy.

### FR-008 — Close vacancy

A Recruiter must be able to close an active vacancy.

A closed vacancy must no longer accept new applications.

Existing Candidates must remain associated with the selection process.

### FR-009 — Vacancy ownership

A Recruiter must only be able to manage vacancies they own or are authorized to manage.

---

# 14. Vacancy States

The MVP should use a small number of explicit vacancy states.

| State | Meaning |
|---|---|
| Draft | Vacancy is being prepared and is not publicly available |
| Published | Vacancy is active and can receive applications |
| Closed | Vacancy is no longer accepting applications |

The MVP should avoid additional states unless operational evidence requires them.

---

# 15. Candidate Experience

## 15.1 Candidate Profile

Candidates do not upload résumés.

Instead, Candidate information is stored directly in the Simpel profile.

The profile should conceptually resemble a lightweight professional profile.

### Required profile data

The MVP should minimize mandatory data.

At minimum, the product needs enough information to:

- identify the Candidate;
- allow Recruiters to understand the Candidate professionally;
- support application and selection workflows.

Potential profile categories include:

- name;
- location;
- professional experience;
- education;
- skills;
- other relevant professional information.

### MVP principle

A field should only be mandatory when it is required for a concrete product workflow.

### Optional information

Additional professional information may be collected where it materially improves Candidate evaluation, but optional data should not become mandatory merely because it is common on professional networks.

---

# 16. Candidate Data Visibility

Candidate information must follow a minimum-necessary principle.

Recruiters should only see Candidate information required to evaluate and manage a Candidate participating in their selection process.

A Recruiter must not receive unrestricted access to unrelated Candidate information.

The exact visibility matrix should be defined before implementation of the final Candidate profile UI.

---

# 17. Job Discovery

## 17.1 Vacancy Discovery

Candidates must be able to discover active vacancies in the "Mural" (a kind of "Wall"), listing the opportunities.

## 17.2 MVP Search / Filters

The MVP should build a sophisticated search engine, offering detailed, specific search fields (the so-called "Filtros Mágicos", in Portuguese), both to the Candidates and to the Recruiters.

Some of these filters, to the Candidates, include:

- location of the office;
- work arrangement;
- employment type;
- job category.

Some of these filters, to the Recruiters, include:

- location of the candidate;
- work experience;
- education;
 
The exact search filtes, either to Candidates or to Recruiters, may be refined for Brazilian Portuguese UX.

## 17.3 Vacancy Card

A vacancy card should communicate enough information to determine whether the Candidate should open the vacancy.

The card should prioritize:

- job title;
- company;
- location;
- work arrangement;
- relevant high-level employment information;
- subscription/visibility indication when applicable.

## 17.4 Vacancy Detail

The vacancy detail page should contain the information necessary for the Candidate to understand the opportunity and decide whether to participate.

The page should clearly distinguish:

- publicly available information;
- subscription-gated information;
- application action;

---

# 18. Subscription-Based Job Access

The business hypothesis requires a meaningful distinction between free and paid Candidate access.

## 18.1 MVP Decision

The subscription should not hide the existence of vacancies.

Free Candidates should be able to discover that an opportunity exists.

The subscription should instead provide **earlier and/or more complete access to relevant opportunity information**.

This preserves the marketplace's ability to attract Candidates while testing whether enhanced access creates willingness to pay.

## 18.2 Early Access

For MVP purposes, "early access" should mean that subscribed Candidates can access eligible vacancy information before that information becomes available to non-subscribed Candidates.

The system therefore needs a clear publication timing rule for eligible vacancies.

## 18.3 Expanded Details

"Expanded job details" should mean additional information intentionally withheld from the free experience.

The gated information should provide meaningful decision value rather than artificially hiding basic vacancy information.

Examples may include additional selection-process information, more complete opportunity context, or other details defined during product validation.

The specific gated fields should be configurable without requiring multiple subscription tiers.

## 18.4 Free Experience

Free Candidates should be able to:

- discover vacancies;
- view publicly available information;
- create a profile;
- apply when application eligibility allows;
- track active selection processes.

## 18.5 Paid Experience

Subscribed Candidates should be able to:

- access eligible early-access opportunities;
- access expanded vacancy details;
- retain normal profile and selection-process functionality.

## 18.6 Subscription Expiration

When a subscription expires:

- access to subscription-only vacancy information should be removed;
- the Candidate's account should remain active;
- existing applications should remain accessible;
- existing selection processes should remain visible;
- the Candidate should not lose previously submitted application data.

The subscription should control access to the premium value, not ownership of the Candidate's account or recruitment history.

---

# 19. Applications / Selection Processes

## 19.1 Application

A Candidate becomes associated with a vacancy when they submit an application.

The application should use the Candidate's existing profile rather than requiring résumé upload.

## 19.2 Selection Process

Each application belongs to one vacancy and one Recruiter's selection process.

The selection process represents the Candidate's current progression.

## 19.3 MVP Stages

The MVP should use a predefined, simple set of stages rather than allowing Recruiters to build arbitrary pipelines.

Recommended stages:

1. Applied
2. In Review
3. Interview
4. Finalist
5. Hired
6. Rejected
7. Withdrawn

The exact stage names may be refined for Brazilian Portuguese UX, but the underlying workflow should remain simple.

## 19.4 Stage Ownership

Recruiters control the Candidate's stage within their vacancy.

Candidates can see the current status but cannot directly modify Recruiter-controlled selection stages.

Candidates should be able to withdraw from an active application.

## 19.5 Candidate Actions

Candidates should be able to:

- apply;
- view their application;
- view current selection status;
- withdraw where appropriate.

## 19.6 Recruiter Actions

Recruiters should be able to:

- view Candidates;
- review Candidate profiles;
- move Candidates between stages;
- reject Candidates;
- recognize a Candidate as hired;
- manage the active selection process.

The MVP does not require sophisticated bulk-processing tools.

---

# 20. Radar

Radar is the central workspace for both user types.

It should not become a generic analytics dashboard.

Its purpose is operational:

> **Show the user what they are currently doing on Simpel and what they can do next.**

---

## 20.1 Recruiter Radar

Recruiter Radar must provide access to:

- active vacancies;
- draft vacancies;
- closed vacancies where relevant;
- Candidates associated with vacancies;
- Candidate selection statuses;
- essential recruitment actions.

The primary workflow should be:

**Vacancy → Candidates → Candidate → Selection Status**

### Recruiter Radar requirements

### FR-010

A Recruiter must be able to see their vacancies from Radar.

### FR-011

A Recruiter must be able to open a vacancy from Radar.

### FR-012

A Recruiter must be able to see Candidates associated with a vacancy.

### FR-013

A Recruiter must be able to see each Candidate's current selection status.

### FR-014

A Recruiter must be able to update a Candidate's selection status.

---

## 20.2 Candidate Radar

Candidate Radar must provide access to:

- active applications;
- selection status;
- relevant actions;
- subscription state where relevant.

The primary workflow should be:

**Application → Selection Process → Current Status → Next Relevant Action**

### Candidate Radar requirements

### FR-015

A Candidate must be able to view all active selection processes in which they are participating from Radar.

### FR-016

A Candidate must be able to view the current status of each application.

### FR-017

A Candidate must be able to access relevant vacancy information from their application.

### FR-018

A Candidate must be able to withdraw from an eligible application.

---

# 21. Subscription & Payments

## 21.1 Payment Provider

Mercado Pago is the payment provider for Candidate subscriptions.

The PRD defines product behavior only; implementation details belong in technical documentation.

## 21.2 Subscription State

The MVP must distinguish at least:

- inactive;
- active;
- expired;
- canceled/pending expiration where applicable;
- payment-failure state where operationally required.

## 21.3 Payment Confirmation

A subscription must only become active after the system receives a reliable payment confirmation from Mercado Pago.

The UI must not grant premium access merely because a Candidate reached a payment page.

## 21.4 Failed Payment

If payment fails:

- premium access must not be granted;
- the Candidate should receive a clear explanation;
- the Candidate should have a reasonable path to retry.

## 21.5 Cancellation

Cancellation must not delete the Candidate's account or applications.

Cancellation affects subscription entitlement according to the payment provider's confirmed subscription state.

## 21.6 Expiration

After expiration:

- premium job access ends;
- Candidate account remains active;
- applications remain accessible;
- selection processes remain accessible.

---

# 22. Trust & Safety

Trust is a core MVP concern because Simpel operates in recruitment.

## 22.1 Corporate Email

Corporate email is the first Recruiter trust signal.

It reduces casual fake-account creation but does not prove:

- company legitimacy;
- Recruiter identity;
- vacancy legitimacy.

Therefore, it must not be presented internally or externally as complete verification.

## 22.2 Recruiter Trust Signal

The MVP should display a simple trust signal indicating that the Recruiter passed Simpel's basic registration requirements.

The signal should not claim stronger verification than the platform actually performed.

## 22.3 Fake Job Prevention

The MVP should combine:

- corporate-email restriction;
- email verification;

The MVP should not attempt to guarantee that every vacancy is legitimate.

---

# 23. Privacy & Data Minimization

Privacy is a product principle, not merely a legal requirement.

## 23.1 Data Minimization

Simpel must collect only data required to:

- operate accounts;
- publish vacancies;
- facilitate applications;
- manage selection processes;
- process subscriptions;
- protect the platform;
- satisfy applicable operational/legal requirements.

## 23.2 Candidate Data

The MVP should avoid collecting personal information that has no clear product purpose.

Candidate data should be limited to information necessary to create a useful professional profile and participate in selection processes.

## 23.3 No Résumé Upload

Simpel should not collect résumé files in the MVP.

This reduces:

- unnecessary document storage;
- duplicated information;
- privacy exposure;
- parsing complexity.

## 23.4 Recruiter Data

Recruiter registration should primarily rely on corporate identity information necessary to operate the account and establish the basic trust mechanism.

## 23.5 Sensitive Information

The MVP should avoid collecting sensitive personal information unless a concrete product or legal requirement justifies it.

The detailed treatment of personal data belongs in `PRIVACY.md`.

## 23.6 Data Access

Users must only access data necessary for their role and relationship to the relevant vacancy or application.

---

# 24. UX Requirements

## 24.1 Language

The interface must use natural Brazilian Portuguese.

Examples of domain terminology include:

- RH;
- Recursos Humanos
- R&S;
- Recrutamento e Seleção;
- Vaga;
- Emprego;
- Candidato;
- Assinante;
- Processo Seletivo;
- Empresa;
- Recrutador;
- Perfil;
- Etapa.

Literal English translations should be avoided when a natural Brazilian Portuguese term exists.

## 24.2 Form Design

Forms should:

- request only necessary information;
- clearly identify required fields;
- provide useful validation;
- avoid unnecessary steps;
- preserve user input when validation fails;
- explain errors in human language.

## 24.3 Responsive Design

The product must work on mobile and desktop layouts.

Candidate discovery in particular must be usable on mobile devices.

## 24.4 Accessibility

The MVP should provide accessible:

- form labels;
- interactive controls;
- keyboard navigation;
- error states;
- readable text;
- meaningful status indicators.

Detailed accessibility standards belong in `DESIGN.md` and implementation documentation.

## 24.5 Human-Washing

The concept of "human-washing" should be translated into product behavior rather than treated as a visual keyword.

Simpel should:

- use human language;
- explain processes clearly;
- avoid robotic or bureaucratic terminology;
- make status changes understandable;
- communicate that Candidates are people rather than records;
- make Recruiters feel they are managing relationships rather than database entries.

The product must remain professional and trustworthy.

It should not become childish, overly playful, or visually distracting.

---

# 25. Non-Functional Requirements

## 25.1 Performance

Core user flows should feel fast and responsive.

Priority flows include:

- authentication;
- vacancy discovery;
- vacancy creation;
- application;
- Radar;
- Candidate status updates.

## 25.2 Reliability

Critical operations must not silently fail.

This includes:

- vacancy publication;
- application submission;
- Candidate status updates;
- subscription activation;
- payment-state synchronization.

## 25.3 Security

The system must enforce authorization at the server/application level.

A user must never gain access to another user's protected data simply by manipulating client-side state or URLs.

## 25.4 Privacy

Personal data must not be exposed to users who are not authorized to access it.

## 25.5 Maintainability

Product rules should be represented in a way that allows future documentation and implementation changes without redefining the core product behavior.

---

# 26. Business Rules

### BR-001 — Recruiter registration

Recruiters must use an eligible corporate email address.

### BR-002 — Consumer email restriction

Known consumer/webmail domains must not be accepted for Recruiter registration.

### BR-003 — Recruiter access

Recruiters can use Simpel without paying a subscription.

### BR-004 — Candidate authentication

Candidates authenticate through Google in the MVP.

### BR-005 — No résumé upload

Candidates do not upload résumés in the MVP.

### BR-006 — Vacancy ownership

Recruiters may only manage vacancies they own or are authorized to manage.

### BR-007 — Closed vacancies

Closed vacancies do not accept new applications.

### BR-008 — Existing applications

Closing a vacancy does not delete existing applications.

### BR-009 — Application uniqueness

A Candidate should not be able to create duplicate active applications for the same vacancy.

### BR-010 — Selection ownership

Recruiters control selection-stage changes.

### BR-011 — Candidate visibility

Candidates can see the current status of their own applications.

### BR-012 — Subscription entitlement

Premium access depends on an active subscription.

### BR-013 — Payment confirmation

Premium access requires confirmed payment status.

### BR-014 — Subscription expiration

Subscription expiration removes premium entitlement but does not delete the Candidate's account or application history.

### BR-015 — Data minimization

The product must not make optional personal information mandatory without a clear product reason.

### BR-016 — Trust claims

Simpel must not claim that corporate-email validation constitutes complete company or Recruiter verification.

---

# 27. Edge Cases

## 27.1 Recruiter Uses Consumer Email

The system rejects registration and explains that a corporate email is required.

## 27.2 Corporate Domain Is Incorrectly Blocked

The product should provide a simple support/review path rather than requiring the user to bypass the restriction.

## 27.3 Recruiter Does Not Complete Vacancy

The vacancy remains a Draft and is not publicly discoverable.

## 27.4 Recruiter Closes Vacancy

New applications are disabled.

Existing Candidates remain accessible.

## 27.5 Candidate Applies Twice

The system prevents duplicate active applications.

## 27.6 Candidate Withdraws

The application changes to Withdrawn.

The Candidate should not automatically be able to recreate the same active application unless product rules explicitly allow it.

## 27.7 Recruiter Rejects Candidate

The Candidate sees the appropriate updated status.

## 27.8 Recruiter Marks Candidate as Hired

The Candidate sees the corresponding final status.

## 27.9 Subscription Payment Fails

Premium access is not activated or is suspended according to the confirmed payment state.

## 27.10 Subscription Expires

Premium information is no longer accessible.

Applications and selection processes remain accessible.

## 27.11 Candidate Profile Changes

Profile changes should affect the Candidate's current profile.

The MVP does not require immutable snapshots of historical profiles unless a concrete operational need emerges.

---

# 28. MVP Acceptance Criteria

## Authentication

### AC-001

A Recruiter using an accepted corporate email can create and access a Recruiter account.

### AC-002

A Recruiter using a blocked consumer email cannot complete registration.

### AC-003

A Candidate can authenticate using Google.

---

## Vacancy Management

### AC-004

A Recruiter can create a Draft vacancy.

### AC-005

A Recruiter can publish a completed vacancy.

### AC-006

A Recruiter can edit an active vacancy.

### AC-007

A Recruiter can close an active vacancy.

### AC-008

A closed vacancy does not accept new applications.

---

## Candidate Experience

### AC-009

A Candidate can create and edit their Simpel professional profile.

### AC-010

A Candidate does not need to upload a résumé to apply.

### AC-011

A Candidate can discover active vacancies.

### AC-012

A Candidate can view the information available to their subscription state.

### AC-013

A Candidate can apply to an eligible vacancy.

### AC-014

A Candidate cannot create duplicate active applications for the same vacancy.

---

## Selection Process

### AC-015

A Recruiter can see Candidates associated with their vacancy.

### AC-016

A Recruiter can update a Candidate's selection status.

### AC-017

A Candidate can see the current status of their application.

### AC-018

A Candidate can withdraw from an eligible application.

---

## Radar

### AC-019

A Recruiter can access their vacancies from Radar.

### AC-020

A Recruiter can access Candidates from a vacancy through Radar.

### AC-021

A Candidate can see their active selection processes in Radar.

### AC-022

A Candidate can open an application from Radar and understand its current status.

---

## Subscription

### AC-023

A Candidate can initiate subscription payment through Mercado Pago.

### AC-024

Premium access is granted only after confirmed payment.

### AC-025

A Candidate without an active subscription cannot access subscription-only information.

### AC-026

An expired subscription removes premium access without deleting the Candidate's account or applications.

---

## Privacy

### AC-027

A Recruiter cannot access unrelated Candidate information.

### AC-028

A Candidate cannot access another Candidate's information.

### AC-029

The MVP does not require résumé-file collection.

---

# 29. Out of Scope

The following are explicitly out of scope for Version 1.2 unless required to solve a demonstrated MVP problem.

## Recruitment Features

- customizable pipelines;
- advanced ATS functionality;
- interview scheduling;
- calendar synchronization;
- automated interview reminders;
- candidate scoring systems;
- AI candidate ranking;
- automated candidate matching;
- résumé parsing;
- résumé storage;
- video interviews.

## Analytics

- advanced Recruiter analytics;
- funnel analytics;
- conversion dashboards;
- time-to-hire reports;
- salary analytics;
- predictive analytics.

## Communication

- advanced messaging systems;
- automated email campaigns;
- marketing automation;
- complex notification workflows.

## Company Management

- enterprise organizations;
- multiple Recruiter permission hierarchies;
- complex team management;
- departmental structures.

## Monetization

- multiple Candidate subscription tiers;
- Recruiter paid plans;
- advertising;
- employer-sponsored placement;
- complex billing models.

## Integrations

- HRIS integrations;
- ATS integrations;
- external job-board syndication;
- calendar integrations;
- résumé databases.

---

# 30. Future Opportunities

These opportunities may become relevant after MVP validation.

## Candidate Features

- richer professional profiles;
- saved vacancies;
- personalized recommendations;
- job alerts;
- advanced search;
- application insights.

## Recruiter Features

- reusable vacancy templates;
- bulk Candidate actions;
- advanced filtering;
- communication tools;
- analytics;
- collaborative recruitment.

## Trust

- stronger company verification;
- verified company profiles;
- enhanced moderation;
- reputation signals.

## Monetization

- additional Candidate subscription tiers;
- Recruiter premium features;
- employer services.

## Automation

- workflow automation;
- intelligent matching;
- AI-assisted vacancy creation;
- AI-assisted Candidate screening.

These features should only be prioritized after evidence that they improve user outcomes or business performance.

---

# 31. Product Risks & Open Questions

## 31.1 Candidate willingness to pay

The central commercial risk is whether Candidates perceive early and expanded job access as valuable enough to justify payment.

**Validation requirement:** Measure conversion and engagement around premium access.

---

## 31.2 Value of Early Access

"Early access" is only valuable if relevant vacancies exist and the timing advantage is meaningful.

The product must validate whether Candidates care about being able to see opportunities earlier.

---

## 31.3 Corporate Email as a Trust Mechanism

Corporate-email validation reduces one type of abuse but does not prove that a vacancy is legitimate.

Simpel should monitor fraud reports and moderation workload.

---

## 31.4 Supply-Side Liquidity

The Candidate subscription hypothesis depends on sufficient vacancy supply.

If there are too few relevant vacancies, premium access will have low perceived value regardless of its implementation.

---

## 31.5 Candidate Profile Completeness

A no-résumé product requires Candidates to maintain useful profile information.

The product must balance:

- sufficient information for Recruiters;
- low Candidate friction;
- privacy.

---

## 31.6 Recruiter Simplicity vs. Functionality

Adding recruitment features may improve Recruiter capability but can undermine the core differentiation of Simpel.

Every new Recruiter feature should be evaluated against the simplicity principle.

---

## 31.7 Subscription Access Rules

The exact definition of which information is premium must be validated before launch.

The MVP should begin with a small, clearly understandable premium boundary.

---

# 32. Assumptions

The following assumptions are necessary to make the MVP definition coherent.

## A-001

Recruiters are individuals representing companies or organizations and are responsible for their published vacancies.

## A-002

Corporate-email validation is an anti-abuse mechanism, not full company verification.

## A-003

Recruiters can use Simpel without paying.

## A-004

Candidates are the primary paying side of the MVP.

## A-005

The Candidate subscription provides early and expanded access rather than completely blocking free users from discovering vacancies.

## A-006

Candidates can still participate in existing selection processes after subscription expiration.

## A-007

Candidates use Google authentication in Version 1.2.

## A-008

Candidates do not upload résumé files.

## A-009

The Candidate profile contains enough structured professional information to substitute for a résumé within the Simpel workflow.

## A-010

Recruitment pipelines are standardized in the MVP rather than fully customizable.

## A-011

Basic moderation can be handled manually during MVP operations.

## A-012

Mercado Pago provides the payment processing infrastructure while Simpel owns the product-level entitlement state.

## A-013

The exact pricing amount is intentionally not fixed by this PRD.

## A-014

The exact premium-information fields are intentionally subject to product validation.

## A-015

The MVP does not require enterprise-grade organizational structures.

---

# 33. Product Metrics

The MVP should focus on a small number of metrics directly connected to its hypotheses.

## Recruiter Metrics

- Recruiter registration completion;
- percentage of Recruiters publishing a first vacancy;
- time from registration to first published vacancy;
- vacancies published per active Recruiter;
- percentage of vacancies receiving applications.

## Candidate Metrics

- Candidate registration completion;
- profile completion;
- vacancy discovery activity;
- application conversion;
- applications per active Candidate;
- selection-process engagement.

## Subscription Metrics

- subscription conversion;
- payment success rate;
- premium-feature engagement;
- subscription retention;
- cancellation rate.

## Marketplace Metrics

- active vacancies;
- applications per vacancy;
- percentage of vacancies receiving at least one Candidate;
- Candidate-to-vacancy activity;
- reported-vacancy rate.

Metrics should remain focused on product validation rather than becoming an analytics project.

---

# 34. Source of Truth & Documentation Boundaries

`PRD.md` is the source of truth for:

- product vision;
- product principles;
- MVP scope;
- user roles;
- functional behavior;
- business rules;
- product workflows;
- acceptance criteria;
- MVP assumptions.

Other documentation should own different concerns.

## `AGENTS.md`

Source of truth for:

- AI coding-agent instructions;
- repository conventions;
- development workflows;
- coding practices;
- implementation constraints.

## `DESIGN.md`

Source of truth for:

- visual identity;
- design system;
- components;
- typography;
- colors;
- spacing;
- interaction patterns;
- detailed accessibility guidance;
- responsive behavior.

## `TERMS.md`

Source of truth for:

- legal terms;
- contractual conditions;
- platform rules;
- legal responsibilities.

## `PRIVACY.md`

Source of truth for:

- personal-data processing;
- privacy practices;
- data rights;
- retention;
- legal privacy requirements;
- detailed data-processing policies.

Technical architecture and implementation details should be documented separately.

---

# 35. MVP Product Principles Checklist

Before adding a feature to Version 1.2, the team should ask:

1. Does this directly support Recruiter vacancy publishing?
2. Does this directly support Candidate job discovery?
3. Does this directly support participation in selection processes?
4. Does this directly support the subscription hypothesis?
5. Does this materially improve trust or safety?
6. Is the feature necessary to operate the MVP?
7. Can the same outcome be achieved more simply?
8. Does the feature introduce unnecessary personal-data collection?
9. Does it create operational complexity disproportionate to its value?
10. Does it belong in `PRD.md`, or should it be defined in another document?

If a feature does not have a strong MVP justification, it should remain out of scope.

---

# 36. Final MVP Definition

Simpel Version 1.2 is a focused two-sided recruitment platform.

A Recruiter can:

> **Register with a corporate email → create a vacancy → publish it → receive Candidates → manage Candidates through a simple selection process → close the vacancy.**

A Candidate can:

> **Sign in with Google → create a lightweight professional profile → discover vacancies → access free or subscription-enabled information → apply → follow the selection process through Radar.**

Simpel's central differentiators are:

1. **Simple Recruiter workflows**
2. **Simple Candidate job discovery**
3. **No résumé uploads**
4. **Privacy-first data collection**
5. **A human-oriented recruitment experience**
6. **A Candidate subscription focused on early and expanded opportunity access**
7. **Basic trust mechanisms for Recruiters and vacancies**
8. **Radar as the central workspace for both sides**

The MVP should resist becoming a conventional ATS, professional social network, or enterprise HR platform.

Its purpose is narrower:

> **Make recruitment simpler.**

The primary product validation question is whether this simpler experience creates enough value for Recruiters to publish and manage vacancies, enough value for Candidates to actively use the platform, and enough differentiated value for Candidates to pay for enhanced access to opportunities.

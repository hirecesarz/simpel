# Simpel — Design System & UX Guidelines

**Document:** `DESIGN.md`
**Version:** 1.2
**Author:** Cesar Zanetti
**E-mail**: hirecesarz at outlook dot com
**Product:** Simpel
**Domain:** `simpelvagas.com`
**Market:** Brazil
**Primary Interface Language:** Brazilian Portuguese
**Code & Documentation Language:** English
**Status:** MVP Design Source of Truth

---

## 1. Purpose

`DESIGN.md` is the authoritative source for Simpel's:

* visual identity;
* design system;
* typography;
* colors;
* spacing;
* layout;
* components;
* interaction patterns;
* responsive behavior;
* accessibility guidance;
* UX principles;
* user-facing interface language;
* frontend design conventions.

It translates the product requirements in `PRD.md` and engineering constraints in `AGENTS.md` into a practical interface system that can be implemented consistently by humans and AI coding agents.

This document is **not** a product specification.

`PRD.md` remains authoritative for:

* product behavior;
* business rules;
* user roles;
* MVP scope;
* functional requirements;
* acceptance criteria;
* product assumptions.

`AGENTS.md` remains authoritative for:

* engineering architecture;
* repository conventions;
* coding practices;
* security;
* deployment;
* technical constraints.

`PRIVACY.md` remains authoritative for detailed privacy requirements.

`TERMS.md` remains authoritative for legal terms.

When this document appears to conflict with another source of truth, the conflict MUST be identified rather than silently resolved.

---

# 2. Design North Star

The most important design principle for Simpel is:

> **Make recruitment technology feel more human without making it less professional.**

The desired user perception is:

> **"This is simple. I understand what is happening. I know what to do next. And there are humans behind this."**

Simpel MUST prioritize:

1. Clarity
2. Human-centered interaction
3. Trust
4. Simplicity
5. Privacy
6. Accessibility
7. Speed
8. Professionalism

Visual sophistication is secondary.

The interface MUST NOT attempt to look sophisticated by accumulating:

* gradients;
* decorative cards;
* dashboards;
* animations;
* colors;
* illustrations;
* badges;
* controls;
* typography styles.

A design decision is successful when it makes the product easier to understand or use.

---

# 3. Design Philosophy

## 3.1 Human + Professional

Simpel's visual personality is:

**warm, editorial, calm, structured, approachable, and professional.**

It is NOT:

* childish;
* cartoonish;
* excessively playful;
* corporate;
* futuristic;
* sterile;
* "AI-looking";
* visually noisy.

The Human-washing direction should communicate warmth without pretending that software is a person.

Human-centered design comes primarily from:

* language;
* clarity;
* respectful interaction;
* contextual feedback;
* visible consequences;
* restrained organic visual details;
* thoughtful whitespace;
* honest status communication.

---

## 3.2 Technology Should Recede

The user should notice:

* the vacancy;
* the candidate;
* the selection process;
* the next action.

The user should not have to notice:

* the framework;
* the component architecture;
* the database model;
* the system's internal terminology;
* unnecessary configuration.

UI complexity MUST be proportional to task complexity.

---

## 3.3 Human-washing Principles

These principles describe a broader visual movement away from cold technology aesthetics toward:

* warmth;
* earthy or softened colors;
* editorial typography;
* organic forms;
* imperfect visual details;
* human imagery;
* hand-drawn or expressive elements.

For Simpel, these principles are translated into:

### Warmth

Use a warm neutral foundation rather than a cold blue-gray SaaS canvas.

### Editorial character

Use typography with enough personality to avoid a generic enterprise dashboard appearance.

### Organic restraint

Small organic details MAY be used for branding, empty states, marketing areas, and selected emphasis.

They MUST NOT interfere with functional UI.

### Imperfection

Slightly human visual details MAY appear in:

* illustrations;
* decorative marks;
* brand accents;
* selected marketing compositions.

Functional controls MUST remain geometrically precise.

### Humanity through clarity

The strongest expression of Human-washing is not decoration.

It is:

> **software that respects the person using it.**

---

# 4. Visual Personality

Simpel should feel like a combination of:

* a thoughtful editorial publication;
* a modern lightweight SaaS;
* a trustworthy recruitment product;
* a calm professional workspace.

It should avoid looking like:

* a traditional ATS;
* an enterprise CRM;
* a financial dashboard;
* an AI laboratory;
* a social network;
* a startup landing page overloaded with effects.

## 4.1 Personality Keywords

Use these as design review criteria:

**Warm**
**Simple**
**Human**
**Clear**
**Calm**
**Trustworthy**
**Useful**
**Professional**
**Approachable**

If a design introduces:

**cold / futuristic / dense / bureaucratic / noisy / childish**

characteristics, reconsider it.

---

# 5. Design Principles

## 5.1 Clarity Over Decoration

Every visual element MUST have a purpose.

Prefer:

> heading → supporting explanation → primary action

over:

> heading → illustration → badge → decorative card → secondary metric → action.

---

## 5.2 One Primary Action

Most screens SHOULD have one visually dominant primary action.

Secondary actions MUST remain visually subordinate.

If everything looks primary, nothing is primary.

---

## 5.3 Reduce Cognitive Load

A user should not have to remember information from one part of a page to complete another part.

Keep:

* labels near controls;
* relevant explanations near decisions;
* status near the affected object;
* actions near the thing they modify.

---

## 5.4 Progressive Disclosure

Do not expose every possible option immediately.

Show the minimum required for the current task.

Reveal secondary information when:

* requested;
* relevant;
* necessary for a decision.

---

## 5.5 Explain State Changes

When something changes, the interface SHOULD make the result obvious.

For example, after moving a Candidate:

* show the new stage;
* provide confirmation;
* preserve context;
* avoid forcing the user to rediscover the Candidate.

---

## 5.6 Respect the User's Work

Forms and workflows MUST:

* preserve entered information where practical;
* avoid unnecessary confirmation;
* avoid unnecessary page transitions;
* avoid surprise behavior;
* avoid destructive actions without adequate warning.

---

## 5.7 No Dark Patterns

Simpel MUST NOT use:

* fake urgency;
* deceptive countdowns;
* misleading button hierarchy;
* disguised advertisements;
* forced subscription framing;
* confusing cancellation;
* hidden premium conditions;
* intentionally ambiguous copy;
* guilt-based messaging.

Subscription conversion MUST be based on clearly communicated value.

---

# 6. Interface Language

## 6.1 Brazilian Portuguese

All user-facing interface content MUST be written in natural Brazilian Portuguese.

This includes:

* navigation;
* headings;
* buttons;
* labels;
* placeholders;
* validation;
* errors;
* notifications;
* empty states;
* loading messages;
* subscription content;
* status labels;
* help text;
* tooltips.

English MUST NOT appear in normal user-facing UI unless it is a proper product, provider, company, or technical name that should remain unchanged.

---

## 6.2 Technical Naming

Technical naming MUST remain in English.

Examples:

```text
Candidate
Recruiter
Vacancy
Application
Subscription
Radar
Button
Modal
Input
StatusBadge
VacancyCard
```

Brazilian Portuguese belongs in user-facing strings, not implementation identifiers.

---

## 6.3 Language Style

Use:

* natural;
* concise;
* respectful;
* direct;
* conversational;
* professional Brazilian Portuguese.

Avoid:

* corporate jargon;
* unnecessary English;
* robotic phrasing;
* legalistic language in normal workflows;
* exaggerated enthusiasm;
* infantilization.

Prefer:

> "Sua candidatura foi enviada."

over:

> "Sua candidatura foi processada com sucesso pelo sistema."

Prefer:

> "Não encontramos vagas com esses filtros."

over:

> "Nenhum resultado foi retornado."

---

# 7. Typography

## 7.1 Typography Direction

Simpel SHOULD use a two-role typography system:

* **Display / editorial typeface:** a distinctive serif;
* **UI / body typeface:** a highly readable sans-serif.

This combination creates the desired Human-washing character without sacrificing usability.

The serif SHOULD be used selectively for:

* major page headings;
* marketing headlines;
* brand storytelling;
* prominent empty-state headlines where appropriate.

The sans-serif MUST remain the primary functional typeface.

---

## 7.2 Recommended Fonts

Recommended default:

* **Display:** DM Serif Display
* **UI:** Inter

Fallback strategy:

```text
DM Serif Display, Georgia, serif
Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif
```

The implementation MAY substitute equivalent fonts if:

* Portuguese glyph coverage is verified;
* readability remains equivalent;
* loading performance improves;
* the design system remains visually consistent.

Do not introduce additional font families without design justification.

---

## 7.3 Font Loading

Fonts MUST be loaded efficiently.

The application SHOULD:

* preload only critical fonts when justified;
* avoid loading unnecessary weights;
* avoid loading multiple unused subsets;
* use `font-display: swap` or an equivalent strategy.

A functional page MUST remain usable while web fonts load.

---

## 7.4 Type Scale

Use a small predictable scale.

Recommended starting scale:

| Token       |     Size | Typical Use                       |
| ----------- | -------: | --------------------------------- |
| `text-xs`   |  0.75rem | Metadata, compact supporting text |
| `text-sm`   | 0.875rem | Labels, secondary text            |
| `text-base` |     1rem | Body text                         |
| `text-lg`   | 1.125rem | Lead/supporting text              |
| `text-xl`   |  1.25rem | Small headings                    |
| `text-2xl`  |   1.5rem | Section headings                  |
| `text-3xl`  | 1.875rem | Page headings                     |
| `text-4xl`  |  2.25rem | Marketing/display                 |
| `text-5xl`  |     3rem | Large hero display only           |

Do not create custom font sizes for individual components unless there is a strong reason.

---

## 7.5 Weight

Use a restrained weight range:

* `400` — regular;
* `500` — medium;
* `600` — semibold;
* `700` — bold, sparingly.

Do not use heavy typography everywhere.

---

## 7.6 Line Height

Recommended:

* body: `1.5–1.7`;
* UI labels: `1.25–1.4`;
* headings: `1.1–1.25`;
* large editorial text: approximately `1.0–1.15`.

Long-form vacancy descriptions SHOULD prioritize readability over compactness.

---

# 8. Color System

## 8.1 Color Direction

Simpel SHOULD use a warm neutral foundation with a restrained earthy brand color.

The palette should feel:

* warm;
* optimistic;
* trustworthy;
* contemporary.

Avoid a conventional blue-heavy SaaS palette.

Avoid neon colors.

Avoid excessive saturation.

---

## 8.2 Core Semantic Tokens

Recommended semantic system:

```text
color-brand
color-brand-hover
color-brand-subtle

color-background
color-surface
color-surface-raised

color-text-primary
color-text-secondary
color-text-muted
color-text-inverse

color-border
color-border-strong

color-success
color-success-subtle
color-warning
color-warning-subtle
color-error
color-error-subtle
color-info
color-info-subtle

color-focus
color-disabled
```

The exact RGB/OKLCH values SHOULD be centralized in the Tailwind theme/token configuration.

Do not scatter raw colors throughout templates.

---

## 8.3 Suggested Palette

A practical initial palette:

| Semantic Role          | Suggested Value                  |
| ---------------------- | -------------------------------- |
| `color-background`     | warm ivory / parchment           |
| `color-surface`        | white or near-white              |
| `color-surface-raised` | white                            |
| `color-text-primary`   | warm charcoal                    |
| `color-text-secondary` | muted warm gray                  |
| `color-border`         | soft warm gray                   |
| `color-brand`          | earthy terracotta / burnt orange |
| `color-brand-hover`    | darker terracotta                |
| `color-brand-subtle`   | pale warm terracotta             |
| `color-success`        | muted green                      |
| `color-warning`        | ochre                            |
| `color-error`          | muted red                        |
| `color-info`           | restrained blue                  |

The final values MUST be validated for WCAG contrast before implementation.

---

## 8.4 Semantic Usage

Never communicate meaning through color alone.

For example, a rejected application MUST include:

* a textual status;
* optionally an icon;
* color as supplementary reinforcement.

---

## 8.5 Color Discipline

A component MUST NOT introduce a new arbitrary color because the existing palette "doesn't look right."

If a new semantic role is required:

1. determine whether an existing token applies;
2. reuse it if possible;
3. otherwise propose a new semantic token;
4. document why it is necessary.

---

# 9. Design Tokens

Design tokens are the shared language between design and implementation.

## 9.1 Token Principles

Tokens MUST be:

* semantic;
* small;
* predictable;
* reusable;
* easy to understand;
* easy for AI agents to reproduce.

Avoid tokens for every visual variation.

---

## 9.2 Spacing

Use a compact spacing scale based on Tailwind's spacing model.

Preferred values:

```text
space-1   0.25rem
space-2   0.5rem
space-3   0.75rem
space-4   1rem
space-5   1.25rem
space-6   1.5rem
space-8   2rem
space-10  2.5rem
space-12  3rem
space-16  4rem
space-20  5rem
space-24  6rem
```

Do not create arbitrary values such as:

```text
17px
23px
29px
37px
```

unless a specific technical requirement exists.

---

## 9.3 Radius

Use a restrained radius system:

```text
radius-sm
radius-md
radius-lg
radius-full
```

Recommended philosophy:

* `sm`: compact controls;
* `md`: inputs, buttons, cards;
* `lg`: larger surfaces and selected feature panels;
* `full`: pills, avatars, circular controls.

Avoid excessive rounded "bubble" interfaces.

---

## 9.4 Borders

Borders SHOULD be subtle.

Default surfaces SHOULD use:

* one consistent border treatment;
* soft neutral color;
* approximately 1px thickness.

Do not combine:

* heavy borders;
* strong shadows;
* large radius;
* saturated backgrounds

on every component.

---

## 9.5 Shadows

Use shadows sparingly.

Preferred hierarchy:

```text
shadow-none
shadow-subtle
shadow-elevated
```

Most cards and panels SHOULD rely on:

> surface + border + spacing

rather than strong shadows.

---

## 9.6 Z-Index

Keep a small predictable hierarchy:

```text
base
dropdown
sticky
overlay
modal
toast
```

Do not invent arbitrary z-index values inside components.

---

## 9.7 Motion Tokens

Recommended:

```text
duration-fast
duration-normal
duration-slow
ease-standard
ease-emphasized
```

Default UI transitions SHOULD be approximately 120–200ms.

Longer motion requires justification.

---

# 10. Layout System

## 10.1 Overall Layout

Simpel should use a centered responsive content system.

Recommended maximum content width:

```text
max-w-7xl
```

Most task-focused screens SHOULD use narrower content widths when appropriate.

For example:

* forms: approximately `max-w-2xl`;
* vacancy details: approximately `max-w-4xl`;
* operational Radar: approximately `max-w-7xl`.

Do not make every page full-width.

---

## 10.2 Page Structure

Typical structure:

```text
Application Shell
├── Header / Navigation
├── Main
│   ├── Page Header
│   ├── Primary Content
│   └── Supporting Content
└── Footer where appropriate
```

Marketing pages MAY use more expressive compositions.

Authenticated product screens SHOULD remain task-oriented.

---

## 10.3 Vertical Rhythm

Use predictable vertical rhythm.

Page sections SHOULD generally use:

```text
space-6
space-8
space-10
space-12
```

Large marketing sections MAY use larger spacing.

Do not compensate for weak hierarchy with excessive whitespace.

---

## 10.4 Grid

Use CSS grid and flexbox through Tailwind.

Typical patterns:

```text
1 column → mobile
2 columns → tablet/desktop
3 columns → desktop only when useful
```

Do not force a grid merely because cards can technically be arranged in one.

---

# 11. Responsive Design

Responsive behavior MUST be designed intentionally.

The application MUST support:

* mobile;
* tablet;
* desktop;
* large desktop.

Suggested conceptual breakpoints:

```text
mobile: < 640px
tablet: 640–1023px
desktop: 1024–1279px
large: >= 1280px
```

Tailwind defaults SHOULD be used unless there is a concrete reason to modify them.

---

## 11.1 Mobile First

The default implementation strategy SHOULD be:

> mobile → tablet → desktop enhancement.

Do not design desktop first and simply shrink it.

---

## 11.2 Mobile Navigation

Desktop navigation MAY use horizontal navigation.

Mobile navigation SHOULD collapse into a simple menu or appropriate compact navigation pattern.

Do not expose a full enterprise navigation system on mobile.

---

## 11.3 Mobile Forms

On mobile:

* inputs SHOULD use the full available width;
* controls SHOULD have comfortable touch targets;
* multi-column forms SHOULD collapse;
* labels MUST remain visible;
* actions SHOULD remain easy to reach.

Avoid horizontal scrolling for normal forms.

---

## 11.4 Mobile Tables

Tables SHOULD NOT simply overflow horizontally when the information can be expressed better as:

* stacked rows;
* compact lists;
* grouped records;
* expandable sections.

Use horizontal scrolling only when preserving tabular relationships is genuinely important.

---

## 11.5 Mobile Radar

Radar SHOULD become a prioritized task list.

Instead of reproducing the desktop layout:

```text
sidebar + table + multiple metrics
```

use:

```text
page context
↓
attention items
↓
relevant records
↓
next action
```

---

# 12. Accessibility

Accessibility is a first-class design requirement.

The implementation SHOULD target WCAG 2.2 AA principles where practical.

---

## 12.1 Semantic HTML

Use semantic elements:

```text
<header>
<nav>
<main>
<section>
<article>
<form>
<button>
<footer>
```

Do not use `<div>` elements as interactive controls when native elements exist.

---

## 12.2 Keyboard Navigation

Every interactive feature MUST be usable with a keyboard.

Keyboard users MUST be able to:

* reach controls;
* understand focus;
* activate actions;
* close dialogs;
* navigate menus;
* submit forms.

---

## 12.3 Focus

Every keyboard-focusable element MUST have a visible focus state.

Focus MUST NOT be removed merely for aesthetic reasons.

Recommended focus treatment:

* clear outline;
* sufficient contrast;
* visible against both light and dark surfaces.

Do not rely on subtle background changes alone.

---

## 12.4 Touch Targets

Interactive targets SHOULD generally provide at least approximately 44×44 CSS pixels of usable touch area.

Small visual icons MAY exist inside larger hit areas.

---

## 12.5 Color Contrast

Text and controls MUST maintain sufficient contrast.

Do not approve a color combination solely because it matches the visual palette.

Contrast is a functional requirement.

---

## 12.6 Reduced Motion

Respect:

```css
prefers-reduced-motion
```

When reduced motion is enabled:

* remove decorative transitions;
* reduce movement;
* avoid parallax;
* avoid animated status indicators unless necessary.

---

## 12.7 Screen Readers

Important state changes MUST be communicated accessibly.

Examples:

* form errors;
* successful application;
* subscription state;
* status updates;
* loading completion.

Use appropriate semantic elements and ARIA only when necessary.

Prefer native semantics over unnecessary ARIA.

---

# 13. UX Principles

## 13.1 The Interface Should Answer Three Questions

At any important point, the user should be able to understand:

1. **Where am I?**
2. **What is happening?**
3. **What can I do next?**

If one is unclear, improve hierarchy or copy.

---

## 13.2 Forms Request Only What Matters

A field MUST NOT be mandatory merely because it is conventional.

Make a field mandatory only when:

* the workflow requires it;
* another user depends on it;
* a business rule requires it;
* a legal/operational requirement requires it.

---

## 13.3 Preserve Context

After an action:

* keep the user near the affected content;
* show the result;
* avoid unnecessary navigation.

---

## 13.4 Avoid Confirmation for Low-Risk Actions

Do not ask:

> "Tem certeza?"

for every action.

Confirmation SHOULD be reserved for actions that are:

* destructive;
* difficult to undo;
* consequential.

---

## 13.5 Destructive Actions

Destructive actions MUST:

* be visually distinct;
* use explicit copy;
* explain consequences when necessary;
* require confirmation when appropriate.

Example:

> "Encerrar vaga"

is preferable to:

> "Excluir"

when the product behavior is actually closing a vacancy.

---

# 14. Forms

Forms are a core Simpel experience.

They MUST feel:

* short;
* calm;
* clear;
* predictable;
* respectful.

---

## 14.1 Form Structure

Preferred structure:

```text
Form title
Short explanation
Field group
Field group
Optional supporting information
Primary action
Secondary action
```

Avoid placing explanatory paragraphs between every field.

---

## 14.2 Labels

Every form control MUST have a visible or programmatically associated label.

Placeholder text MUST NOT be the only label.

---

## 14.3 Required Fields

Required fields MUST be clearly identified.

Optional fields MAY be explicitly labeled where ambiguity exists.

Do not mark every field as optional if only a few are optional.

---

## 14.4 Help Text

Help text SHOULD answer:

> "Why does this field matter?"

when the answer is not obvious.

Keep help text short.

---

## 14.5 Validation

Prefer inline validation when:

* the user has completed a field;
* immediate feedback is useful;
* the error is unambiguous.

Do not aggressively validate while a user is still typing.

---

## 14.6 Error Messages

An error should explain:

1. what happened;
2. what needs to change;
3. how to fix it.

Bad:

> "Campo inválido."

Better:

> "Informe uma localização para publicar a vaga."

---

## 14.7 Preserve Input

When validation fails, preserve valid user input.

Never make users re-enter an entire form because one field failed.

---

## 14.8 Multi-Step Forms

Use multistep forms only when a single screen would create excessive cognitive load.

Each step SHOULD:

* have a clear purpose;
* expose only relevant fields;
* show progress when useful;
* allow returning without losing information.

---

# 15. Buttons & Actions

## 15.1 Hierarchy

Use five primary action types:

### Primary

Main action for the current task.

### Secondary

Important but subordinate action.

### Tertiary

Low-emphasis action.

### Destructive

Action that removes, closes, rejects, or otherwise has significant consequences.

### Link

Navigation or inline contextual action.

---

## 15.2 Button Copy

Use explicit Brazilian Portuguese verbs.

Prefer:

* "Publicar vaga"
* "Salvar rascunho"
* "Aplicar para esta vaga"
* "Atualizar etapa"
* "Encerrar vaga"
* "Assinar agora"
* "Ver detalhes"

Avoid:

* "OK"
* "Enviar"
* "Continuar"
* "Confirmar"

when the exact action can be named.

---

## 15.3 Button States

Every button that triggers an operation SHOULD support:

```text
default
hover
focus
active
disabled
loading
```

Loading states MUST prevent accidental duplicate submissions when appropriate.

Example:

> "Publicando…"

rather than leaving the user wondering whether the click worked.

---

# 16. Navigation

Navigation MUST remain minimal.

Simpel has two distinct primary product contexts.

---

## 16.1 Recruiter Navigation

Recommended conceptual navigation:

```text
Radar
Vagas
Candidatos
Perfil / Conta
```

Do not create separate top-level navigation items for every small feature.

---

## 16.2 Candidate Navigation

Recommended conceptual navigation:

```text
Mural
Radar
Perfil
Assinatura / Conta
```

The exact labels MAY evolve with UX validation.

---

## 16.3 Navigation Rules

The active location MUST be understandable.

Avoid:

* deeply nested menus;
* enterprise-style sidebars;
* five-level navigation;
* navigation items that exist only for one rare action.

---

# 17. Radar

Radar is the central operational workspace.

It is NOT an analytics dashboard.

Its core question is:

> **"O que está acontecendo e o que precisa da minha atenção?"**

---

## 17.1 Recruiter Radar

Primary hierarchy:

```text
Vacancies
↓
Candidates
↓
Candidate
↓
Selection Status
↓
Next Action
```

The Radar SHOULD prioritize:

1. active vacancies;
2. candidate activity;
3. current selection statuses;
4. actions requiring attention.

Draft and closed vacancies MAY remain accessible but SHOULD have lower visual prominence.

---

## 17.2 Candidate Radar

Primary hierarchy:

```text
Applications
↓
Selection Process
↓
Current Status
↓
Next Relevant Action
```

Each application should answer:

* qual é a vaga?
* qual é a empresa?
* em que etapa estou?
* há alguma ação disponível?

---

## 17.3 Status Visualization

Use a combination of:

* status label;
* typography;
* subtle color;
* optional icon.

Do not build elaborate workflow diagrams.

A simple sequence MAY be useful for a selection process:

```text
Candidatura
→ Em análise
→ Entrevista
→ Finalista
→ Contratado
```

but it SHOULD remain readable and not imply progress when the state is actually uncertain.

---

## 17.4 Radar Empty State

Empty Radar states SHOULD explain:

* why nothing is shown;
* what the user can do next.

Example:

> **"Seu Radar está tranquilo por enquanto."**
> "Quando você publicar uma vaga ou se candidatar a uma oportunidade, ela aparecerá aqui."

Avoid:

> "No data found."

---

## 17.5 Radar Is Not Analytics

Do NOT introduce:

* vanity metrics;
* large KPI tiles;
* unnecessary charts;
* conversion graphs;
* decorative data visualizations.

A metric belongs in Radar only if it directly helps the user act.

---

# 18. Mural / Job Discovery

"Mural" is the Candidate vacancy discovery experience defined by the PRD.

It should feel more like browsing opportunities than operating a database.

---

## 18.1 Vacancy Card

A vacancy card SHOULD prioritize:

1. job title;
2. company;
3. location;
4. work arrangement;
5. employment type;
6. meaningful high-level information;
7. relevant subscription indication.

The card SHOULD NOT attempt to contain the entire vacancy.

---

## 18.2 Card Density

A vacancy card SHOULD be scannable in approximately a few seconds.

Use:

* strong title;
* compact metadata;
* predictable spacing;
* one clear entry action.

Avoid:

* excessive badges;
* multiple CTA buttons;
* long descriptions;
* unnecessary company statistics.

---

## 18.3 Search

Search SHOULD remain simple enough to understand immediately.

The user should be able to answer:

> "What am I searching for?"

without learning a query language.

---

## 18.4 Filtros Mágicos

The PRD identifies sophisticated discovery/filtering as an important MVP requirement.

Despite the playful name, the UI MUST NOT become complicated.

Filters SHOULD be:

* grouped logically;
* understandable in Brazilian Portuguese;
* easy to clear;
* visible when active;
* responsive on mobile.

Candidate filter groups MAY include:

* localização;
* modelo de trabalho;
* tipo de contratação;
* categoria da vaga.

Recruiter filters MAY include:

* localização do candidato;
* experiência;
* formação.

The final filter set should remain aligned with the product's validated requirements.

---

## 18.5 Mobile Filters

On mobile, filters SHOULD open in:

* a dedicated filter sheet;
* a dialog;
* another focused full-width interaction.

Do not squeeze a desktop filter bar into a narrow screen.

---

# 19. Vacancy Details

A vacancy detail page must help a Candidate decide:

> **"Quero participar desta oportunidade?"**

---

## 19.1 Information Hierarchy

Recommended:

```text
Job title
Company
Location / work arrangement
Employment information
Primary action
Main description
Requirements
Additional information
Subscription boundary where applicable
```

---

## 19.2 Subscription Gating

Premium information MUST be clearly distinguished.

The UI MUST communicate:

* what is available;
* what is restricted;
* why it matters;
* what the subscription provides.

Do not blur, obscure, or intentionally degrade information merely to create frustration.

---

## 19.3 Gated Content

Premium boundaries SHOULD be visually calm.

Preferred pattern:

```text
Available information

──────────────

Additional opportunity information
[subscription explanation]
[Ver / acessar com assinatura]
```

Avoid:

* fake locked screenshots;
* artificial urgency;
* misleading "exclusive" language;
* aggressive overlays.

---

# 20. Subscription UX

Subscription messaging must communicate value honestly.

A Candidate should understand:

> "O que recebo em troca?"

before subscribing.

---

## 20.1 Subscription States

The UI SHOULD clearly distinguish:

* inactive;
* active;
* pending/canceling where relevant;
* expired;
* payment failed.

Never rely only on color.

---

## 20.2 Payment Transition

After a Candidate starts payment:

* explain what is happening;
* avoid claiming activation before confirmation;
* show a pending state when appropriate.

The interface MUST follow the confirmed entitlement state defined by the product.

---

## 20.3 Expiration

When premium access expires:

* explain that premium access ended;
* preserve the Candidate's account;
* preserve applications;
* preserve selection processes.

Do not imply that the user's recruitment history has been deleted.

---

# 21. Recruiter Experience

Recruiter workflows should feel operational rather than bureaucratic.

The primary task is:

> **create a useful vacancy and manage people through the process.**

---

## 21.1 Vacancy Creation

The vacancy creation flow SHOULD feel like a guided conversation with a clear structure rather than an enterprise configuration screen.

Recommended grouping:

### Opportunity

* job title;
* company;
* location;
* work arrangement;
* employment type.

### Compensation

* salary information.

### Description

* responsibilities;
* requirements;
* relevant context.

The exact field specification remains governed by the PRD.

---

## 21.2 Draft State

Saving a draft SHOULD be easy.

The user should be able to leave without publishing.

The UI SHOULD make the state explicit:

> "Rascunho"

rather than implying that the vacancy is live.

---

## 21.3 Publication

Before publishing, the interface SHOULD provide a concise review.

The review should answer:

* what will Candidates see?
* what information is missing?
* is this ready to publish?

Do not create an unnecessarily elaborate wizard.

---

# 22. Candidate Experience

Candidates should feel like participants, not database records.

---

## 22.1 Candidate Profile

The profile SHOULD feel like a lightweight professional identity.

Do not reproduce a full social network.

Do not require unnecessary fields.

Use sections such as:

* Sobre;
* Experiência;
* Formação;
* Habilidades.

Only include sections supported by the actual product requirements.

---

## 22.2 No Résumé Upload

The interface MUST NOT encourage Candidates to upload résumés in the MVP.

Do not include:

* "Anexe seu currículo";
* "Envie seu CV";
* résumé upload components.

The product's differentiation is the structured professional profile.

---

## 22.3 Application

Application should be low friction.

If the Candidate already has the required profile information, the system SHOULD avoid asking them to repeat it.

The primary action should be obvious.

After application:

> **"Candidatura enviada."**

Then explain what happens next when useful.

---

# 23. Selection Status

Selection statuses should be understandable in Brazilian Portuguese.

Suggested presentation labels:

| Internal Concept | User-Facing Label    |
| ---------------- | -------------------- |
| Applied          | Candidatura enviada  |
| In Review        | Em análise           |
| Interview        | Entrevista           |
| Finalist         | Finalista            |
| Hired            | Contratado           |
| Rejected         | Não selecionado      |
| Withdrawn        | Candidatura retirada |

These are presentation labels only.

Underlying state names remain defined by the product and engineering documentation.

---

## 23.1 Status Honesty

Do not use language that implies more certainty than the actual state provides.

For example:

> "A empresa está analisando sua candidatura."

is preferable to:

> "Você está quase contratado."

---

# 24. Components

The design system should remain intentionally small.

Core components:

```text
Button
Link
Input
Textarea
Select
Checkbox
Radio
FormField
FormError
FormHelp
Badge
StatusBadge
Alert
Toast
Card
VacancyCard
Modal
Dialog
Dropdown
Tabs
Breadcrumbs
Pagination
List
Table
Avatar
EmptyState
LoadingState
Skeleton
Navigation
PageHeader
FilterBar
FilterSheet
StatusTimeline
```

Not every component needs multiple variants.

---

# 25. Component Rules

Every reusable component MUST answer:

1. What problem does it solve?
2. When should it be used?
3. When should it not be used?
4. What states does it support?
5. How does it behave responsively?
6. How is it accessible?

If these questions cannot be answered, the component probably does not need to exist.

---

## 25.1 Button

Use for actions.

Do not use buttons for navigation when a normal link is semantically correct.

---

## 25.2 Link

Use for navigation.

Links MUST look and behave like links.

Do not style every link as a button.

---

## 25.3 Input

Inputs MUST support:

* label;
* optional help;
* error;
* disabled;
* focus;
* loading/read-only where relevant.

---

## 25.4 Select

Use native `<select>` unless a custom interaction provides meaningful value.

Do not replace native controls merely for visual novelty.

---

## 25.5 Badge

Badges SHOULD communicate compact categorical information.

Do not turn every piece of metadata into a badge.

---

## 25.6 StatusBadge

Use for states such as:

* Publicada;
* Rascunho;
* Encerrada;
* Em análise;
* Entrevista;
* Contratado.

Status badges MUST include text.

---

## 25.7 Alert

Use for contextual information that deserves attention.

Examples:

* payment failure;
* blocked corporate email;
* important account state.

---

## 25.8 Toast

Use for short-lived feedback.

Toasts MUST NOT be the only place where critical information exists.

For example, a successful application should have a persistent result in the relevant workflow in addition to transient feedback when appropriate.

---

## 25.9 Modal / Dialog

Use only when the user needs to make a focused decision without losing page context.

Do not put complex multistep workflows into modals.

Dialogs MUST:

* have a meaningful title;
* manage focus;
* support keyboard closing;
* restore focus appropriately.

---

## 25.10 EmptyState

An empty state should contain:

1. context;
2. explanation;
3. next action when one exists.

---

## 25.11 Skeleton

Skeletons MAY be used when content loading is long enough that perceived responsiveness benefits.

Do not use skeletons for instantaneous operations.

---

# 26. States & Feedback

Every interactive component SHOULD define:

```text
Default
Hover
Focus
Active
Disabled
Loading
Success
Warning
Error
Empty
```

Not every component needs every state visually, but every state relevant to its behavior MUST be considered.

---

## 26.1 Loading

Loading feedback should communicate:

> "The system is working."

It should not create unnecessary movement.

---

## 26.2 Success

Success feedback should communicate:

* what happened;
* what is now true;
* what the user can do next.

---

## 26.3 Error

Errors should be calm and actionable.

Avoid:

> "Erro fatal."

Prefer:

> "Não conseguimos publicar a vaga agora. Seus dados foram mantidos. Tente novamente."

---

## 26.4 Empty

Empty does not necessarily mean failure.

Distinguish:

* first use;
* no results;
* no activity;
* unavailable;
* error.

These are different states and should not share one generic message.

---

# 27. Icons

Use a single consistent icon library if an icon library is required.

A lightweight SVG icon set SHOULD be preferred over introducing multiple libraries.

Icons SHOULD:

* support comprehension;
* have consistent stroke/weight;
* align visually with typography;
* include accessible labels when necessary.

Do not use icons for every button.

Text should remain when the action is not obvious.

---

# 28. Imagery & Illustration

Simpel does not need constant imagery.

Use imagery strategically.

Appropriate uses:

* landing pages;
* brand storytelling;
* selected empty states;
* trust communication;
* editorial moments.

Avoid stock photography simply to fill space.

If photography is used, favor:

* real people;
* natural environments;
* documentary/editorial feeling;
* warm and authentic compositions.

Avoid:

* exaggerated corporate handshakes;
* artificial office smiles;
* overly staged recruitment imagery;
* generic "technology" imagery.

---

# 29. Organic Visual Language

Organic elements MAY include:

* hand-drawn lines;
* imperfect shapes;
* subtle paper-like textures;
* editorial crops;
* soft asymmetry;
* simple illustrated marks.

They SHOULD be used primarily in:

* marketing;
* empty states;
* brand surfaces;
* onboarding.

Functional screens MUST remain structurally precise.

Do not add hand-drawn effects to:

* buttons;
* form fields;
* tables;
* navigation controls;
* status indicators.

Human does not mean imprecise.

---

# 30. Motion

Motion should be calm and functional.

Use motion to communicate:

* state change;
* continuity;
* hierarchy;
* feedback.

Do not use motion merely because a component can animate.

---

## 30.1 Recommended Motion

Appropriate:

* button loading;
* dropdown opening;
* dialog entrance;
* toast entrance;
* subtle hover transition;
* filter panel transition.

Avoid:

* bouncing;
* excessive parallax;
* looping decorative animation;
* long page transitions;
* animated dashboards.

---

# 31. Privacy & Trust in UI

Privacy is a product principle.

The interface should communicate it through behavior rather than exaggerated claims.

---

## 31.1 Visibility

When relevant, tell the user:

> "Quem pode ver isso?"

Examples:

> "Visível para empresas quando você se candidata."

or:

> "Essas informações são usadas para completar seu perfil profissional."

Do not force users to infer visibility from context.

---

## 31.2 Trust Signals

Recruiter trust signals MUST be accurate.

Do not display:

> "Empresa verificada"

if the system only verified a corporate email.

Prefer language that reflects the actual mechanism, such as:

> "Cadastro com e-mail corporativo"

when that is the true signal.

---

## 31.3 Privacy Messaging

Privacy explanations SHOULD be:

* short;
* specific;
* close to the relevant decision.

Avoid large generic privacy paragraphs in normal workflows.

Detailed requirements belong in `PRIVACY.md`.

---

# 32. Content Density

Simpel should use **meaningful density**.

Avoid both:

### Excessive density

* many controls;
* tiny typography;
* dense tables;
* too many badges;
* insufficient whitespace.

### Excessive sparsity

* huge empty spaces;
* hidden information;
* unnecessary page navigation;
* oversized cards;
* oversized headings.

The correct density allows users to scan and act without feeling overwhelmed.

---

# 33. Tables & Lists

Tables SHOULD be used only when comparison across rows and columns is useful.

For most recruitment workflows, lists MAY be preferable.

Recruiter candidate management should prioritize:

* candidate identity;
* relevant professional information;
* current status;
* next action.

Do not create enterprise-style tables containing every available field.

---

# 34. Cards

Cards are grouping mechanisms, not the default layout primitive.

Use cards when they provide:

* meaningful grouping;
* independent interaction;
* visual separation;
* scanning benefit.

Do NOT put every UI section inside a card.

A page composed of:

```text
card inside card inside card inside card
```

should be considered a design smell.

---

# 35. Breadcrumbs

Breadcrumbs SHOULD be used only when hierarchy becomes meaningful.

They are generally unnecessary for:

* Mural;
* simple Radar pages;
* basic account pages.

They MAY be useful for deeper vacancy/recruiter contexts.

---

# 36. Pagination

Pagination SHOULD be used for collections that can grow significantly.

The interface SHOULD clearly communicate:

* current position;
* navigation;
* total context when useful.

On mobile, controls MUST remain easy to operate.

---

# 37. Microcopy System

Microcopy should sound like a thoughtful human wrote it.

## 37.1 Buttons

Use verbs:

* "Publicar vaga"
* "Salvar"
* "Editar perfil"
* "Aplicar"
* "Ver candidatura"
* "Atualizar etapa"
* "Encerrar vaga"

---

## 37.2 Empty States

Instead of:

> "Nenhuma vaga encontrada."

Prefer contextual wording:

> **"Ainda não encontramos uma vaga para esses filtros."**
> "Tente ajustar localização, modelo de trabalho ou categoria."

---

## 37.3 Success

Prefer:

> **"Tudo certo. Sua vaga foi publicada."**

over:

> "Operação realizada com sucesso."

---

## 37.4 Errors

Prefer:

> "Não conseguimos salvar agora. Seus dados continuam preenchidos. Tente novamente."

over:

> "Erro 500."

---

## 37.5 Loading

Use loading messages only when useful.

Examples:

> "Publicando vaga…"

> "Atualizando candidatura…"

Do not write:

> "Processando dados…"

when the actual operation can be named.

---

# 38. Recruiter Trust Copy

Avoid overclaiming.

Do not say:

> "Recrutador verificado."

unless the platform has actually performed the corresponding verification.

Avoid:

> "Vaga 100% segura."

No recruitment marketplace can guarantee this.

Use precise language.

---

# 39. Candidate Respect

Candidate-facing copy MUST avoid reducing people to pipeline objects.

Prefer:

> "Sua candidatura está em análise."

over:

> "Seu registro está no estágio 2."

Prefer:

> "A empresa atualizou sua candidatura."

over:

> "O objeto Application foi atualizado."

The interface can expose process terminology when useful, but the dominant language should remain human.

---

# 40. Performance

The design system MUST remain lightweight.

---

## 40.1 Fonts

Do not load unnecessary fonts or weights.

---

## 40.2 Images

Images SHOULD:

* use appropriate dimensions;
* use modern formats where practical;
* be lazy-loaded when not immediately visible;
* include meaningful alternative text where appropriate.

---

## 40.3 Icons

Prefer lightweight SVG icons.

Avoid loading large icon font libraries when a small SVG set is sufficient.

---

## 40.4 CSS

Tailwind is the primary styling mechanism.

Do not create a large parallel custom CSS framework.

Custom CSS SHOULD be limited to:

* genuinely complex visual requirements;
* browser-specific behavior;
* design-system primitives that Tailwind cannot express cleanly.

---

## 40.5 JavaScript

Alpine.js SHOULD be used only where interaction requires client-side behavior.

Do not create JavaScript state for information that Django can render directly.

---

## 40.6 Third-Party Assets

Third-party visual dependencies SHOULD be minimized.

Before adding a visual dependency, ask:

1. Is it necessary?
2. Can the existing stack provide it?
3. Does it increase page weight?
4. Does it introduce privacy or supply-chain concerns?
5. Will AI agents be able to reproduce its usage consistently?

---

# 41. Frontend Implementation

The frontend architecture is defined by `AGENTS.md`.

The design system MUST be implemented using:

* Django templates;
* Tailwind;
* Alpine.js where needed;
* server-rendered HTML;
* progressive enhancement.

Do not introduce React, Vue, Angular, Svelte, or another frontend framework for MVP.

---

## 41.1 Tailwind

Tailwind SHOULD be the primary implementation mechanism.

Prefer:

```html
class="..."
```

using established design tokens and utilities.

Do not introduce arbitrary styling when an existing utility or token provides the correct behavior.

---

## 41.2 Design Tokens in Tailwind

Semantic tokens SHOULD map into Tailwind's theme configuration.

Conceptually:

```text
color-brand
color-text-primary
color-surface
color-border
space-4
radius-md
shadow-subtle
```

The implementation MUST avoid hard-coded semantic colors throughout templates.

---

## 41.3 Custom CSS

Custom CSS MAY be used when:

* a repeated visual primitive cannot be expressed cleanly with Tailwind;
* a browser behavior requires it;
* typography or editorial styling needs controlled CSS.

Custom CSS MUST NOT become a second styling system.

---

# 42. Django Template Components

Reusable components SHOULD live in the project's shared template component structure defined by `AGENTS.md`.

Examples:

```text
components/button.html
components/input.html
components/status_badge.html
components/vacancy_card.html
components/empty_state.html
components/modal.html
```

Component names MUST remain in English.

User-facing content inside components MUST be Brazilian Portuguese.

---

# 43. Component Composition

Prefer composition over duplication.

Example:

```text
Page
└── PageHeader
    ├── Title
    ├── Description
    └── Actions
```

Do not create a new component for every nested visual element.

---

# 44. Alpine.js

Alpine.js SHOULD handle small interactions such as:

* dropdowns;
* modal visibility;
* mobile navigation;
* filter sheets;
* tabs;
* small progressive-enhancement behaviors.

Alpine.js MUST NOT become the primary application state manager.

Server-side product state remains authoritative.

---

# 45. AI Coding-Agent Rules

AI agents MUST treat `DESIGN.md` as the design source of truth.

Before implementing a new interface:

1. Read `PRD.md`.
2. Read relevant sections of `AGENTS.md`.
3. Read relevant sections of `DESIGN.md`.
4. Inspect existing components.
5. Reuse existing patterns.
6. Implement only what the product requires.
7. Verify responsive behavior.
8. Verify accessibility.
9. Verify Brazilian Portuguese.
10. Review visual consistency.

---

## 45.1 Agents MUST

* reuse existing design tokens;
* reuse existing components;
* use semantic HTML;
* preserve responsive behavior;
* provide visible focus states;
* use Brazilian Portuguese in user-facing UI;
* keep technical naming in English;
* preserve form input on validation failures;
* handle loading/error/empty states;
* respect privacy-related visibility;
* follow `PRD.md`;
* follow `AGENTS.md`.

---

## 45.2 Agents MUST NOT

* invent new colors unnecessarily;
* invent new typography;
* create arbitrary spacing values;
* create duplicate components;
* introduce another CSS framework;
* introduce another frontend framework;
* add unnecessary animations;
* use placeholder production UI;
* bypass accessibility;
* create dark patterns;
* add unnecessary user data fields;
* expose unauthorized information;
* introduce enterprise-style dashboard complexity.

---

# 46. Design Evolution Rules

The design system MUST evolve deliberately.

A new feature MUST fit existing:

* colors;
* typography;
* spacing;
* radius;
* borders;
* shadows;
* interaction patterns;
* component vocabulary.

A new visual pattern MAY be introduced only when:

1. an existing pattern cannot adequately solve the problem;
2. the new pattern improves UX;
3. it is reusable;
4. accessibility is considered;
5. it does not unnecessarily increase complexity.

---

# 47. New Component Decision Rule

Before creating a new component, ask:

> **Can an existing component express this interaction without becoming confusing?**

If yes, reuse it.

If no, create a new component only when the pattern is likely to recur or represents a meaningful product interaction.

Do not create:

```text
PrimaryButtonV2
ModernButton
SpecialButton
DashboardButton
RecruiterButton
CandidateButton
```

when a semantic button variant is sufficient.

---

# 48. New Token Decision Rule

Before adding a token:

1. Is an existing semantic token appropriate?
2. Is this difference meaningful?
3. Will it recur?
4. Does it represent a genuine design role?
5. Can the difference be expressed through an existing variant?

If not, add the smallest semantic token necessary.

---

# 49. Design QA Checklist

Every significant frontend change MUST be reviewed against the following checklist.

## Product

* [ ] Aligned with `PRD.md`
* [ ] Does not introduce out-of-scope behavior
* [ ] Correct user role
* [ ] Correct product terminology
* [ ] Correct business-state representation

## Visual

* [ ] Uses existing colors
* [ ] Uses existing typography
* [ ] Uses existing spacing
* [ ] Uses existing components
* [ ] Does not introduce unnecessary cards
* [ ] Does not introduce unnecessary decoration

## Responsive

* [ ] Mobile layout works
* [ ] Tablet layout works
* [ ] Desktop layout works
* [ ] Touch targets are usable
* [ ] No accidental horizontal overflow
* [ ] Navigation works at all supported sizes

## Accessibility

* [ ] Semantic HTML
* [ ] Labels associated with controls
* [ ] Keyboard navigation
* [ ] Visible focus
* [ ] Sufficient contrast
* [ ] Color is not the only status signal
* [ ] Dialogs manage focus
* [ ] Reduced motion considered

## States

* [ ] Default
* [ ] Hover where relevant
* [ ] Focus
* [ ] Disabled where relevant
* [ ] Loading where relevant
* [ ] Error
* [ ] Empty
* [ ] Success where relevant

## Content

* [ ] Brazilian Portuguese
* [ ] Natural language
* [ ] No unnecessary jargon
* [ ] No artificial enthusiasm
* [ ] Actions use specific verbs
* [ ] Privacy/visibility is understandable

## Engineering

* [ ] Uses Tailwind appropriately
* [ ] Uses Alpine only when necessary
* [ ] Reuses Django template components
* [ ] No unnecessary dependency
* [ ] No duplicate styling system
* [ ] No unauthorized client-side assumptions

---

# 50. AI Acceptance Checklist

An AI coding agent SHOULD consider a frontend task complete only when all applicable answers are "yes":

```text
[ ] Did I read the relevant PRD requirement?
[ ] Did I follow AGENTS.md?
[ ] Did I reuse an existing component?
[ ] Did I reuse existing tokens?
[ ] Is the interface in Brazilian Portuguese?
[ ] Is the implementation responsive?
[ ] Is the HTML semantic?
[ ] Can keyboard users operate it?
[ ] Is focus visible?
[ ] Are errors understandable?
[ ] Is the loading state handled?
[ ] Is the empty state handled?
[ ] Is the success state handled?
[ ] Is color insufficient as the sole state signal?
[ ] Did I avoid unnecessary visual complexity?
[ ] Did I avoid unnecessary user-data collection?
[ ] Did I avoid introducing a new dependency?
[ ] Does the result feel like Simpel rather than a generic SaaS?
```

---

# 51. Design Anti-Patterns

The following patterns SHOULD be treated as design smells.

## 51.1 Enterprise Dashboard Syndrome

Symptoms:

* KPI tiles everywhere;
* charts without decisions;
* dense tables;
* multiple sidebars;
* dozens of filters;
* excessive navigation.

Response:

> Simplify the workflow around the user's immediate task.

---

## 51.2 Card Everything

Symptoms:

* every section is a card;
* cards nested inside cards;
* no visual hierarchy outside containers.

Response:

> Remove containers that do not improve grouping.

---

## 51.3 Color Explosion

Symptoms:

* different colors for every category;
* arbitrary accent colors;
* gradients used for emphasis.

Response:

> Return to semantic tokens.

---

## 51.4 Human-Washing as Decoration

Symptoms:

* random scribbles;
* paper textures everywhere;
* illustrations replacing useful information;
* childish visual language.

Response:

> Move the human quality into copy, hierarchy, interaction, and restraint.

---

## 51.5 AI Aesthetic

Avoid visual clichés such as:

* neon gradients;
* glowing borders;
* futuristic grids;
* excessive dark mode;
* "AI magic" animations;
* holographic UI.

Simpel is a recruitment product, not an AI laboratory.

---

## 51.6 Generic SaaS Aesthetic

Avoid creating an indistinguishable interface using:

* default blue;
* Inter everywhere;
* identical rounded cards;
* generic dashboard templates.

The visual system should have a recognizable Simpel personality.

---

# 52. Marketing vs Product UI

The visual system MAY be more expressive in public-facing marketing pages.

Marketing may use:

* larger serif typography;
* organic illustrations;
* expressive layouts;
* editorial imagery;
* stronger brand moments.

Authenticated product workflows SHOULD remain more restrained.

The same brand language must remain recognizable across both.

---

# 53. Trust-Critical Interfaces

Extra care is required for:

* Recruiter registration;
* corporate-email validation;
* vacancy publication;
* subscription/payment;
* application submission;
* candidate status;
* privacy/visibility;
* moderation/reporting.

These interfaces MUST prioritize:

* clarity;
* accurate expectations;
* state visibility;
* error recovery;
* honest messaging.

Do not optimize these screens primarily for conversion.

Trust is more important than persuasion.

---

# 54. Privacy-Critical Interfaces

When displaying personal or professional information:

* show only what is necessary;
* make visibility understandable;
* avoid unnecessary duplication;
* do not expose unrelated information;
* avoid unnecessary profile completeness pressure.

A design that makes more information visible merely because it "looks useful" violates Simpel's privacy-first philosophy.

---

# 55. Performance-Critical Interfaces

The following are especially performance-sensitive:

* Mural;
* vacancy details;
* Radar;
* authentication;
* application;
* subscription.

These screens SHOULD prioritize:

* fast initial rendering;
* limited JavaScript;
* optimized assets;
* minimal third-party dependencies.

Do not introduce visual effects that materially slow core workflows.

---

# 56. Open Questions & Assumptions

The following decisions remain intentionally open because the supplied product documentation does not fully specify them.

## 56.1 Final Brand Color Values

This document establishes the semantic direction:

> warm neutral + restrained earthy brand accent.

Exact production values MUST be validated through accessibility and visual QA before being considered final.

---

## 56.2 Final Font Hosting Strategy

The recommended typography uses Google Fonts-compatible families, but the final implementation SHOULD evaluate:

* Google Fonts;
* self-hosting;
* privacy implications;
* loading performance;
* Portuguese glyph coverage.

The choice should not change the typography roles defined here.

---

## 56.3 Exact Premium Information

The PRD intentionally leaves the exact premium fields open.

`DESIGN.md` therefore defines the **interaction pattern** but MUST NOT invent the final premium information.

---

## 56.4 Candidate Visibility Matrix

The PRD requires minimum-necessary Candidate visibility but indicates that the exact matrix should be defined before final profile UI implementation.

The interface MUST follow the eventual approved visibility matrix.

---

## 56.5 Final Filter Taxonomy

The PRD establishes the importance of "Filtros Mágicos" but allows the exact filter set to be refined.

The design system therefore defines how filters behave, not an immutable list of every filter.

---

# 57. Cross-Document Boundaries

## `PRD.md`

Owns:

* product requirements;
* business behavior;
* MVP scope;
* user journeys;
* product states;
* business rules.

## `AGENTS.md`

Owns:

* architecture;
* implementation;
* security;
* testing;
* deployment;
* technical conventions.

## `DESIGN.md`

Owns:

* UX;
* UI;
* visual identity;
* design tokens;
* components;
* responsive behavior;
* accessibility;
* interaction patterns;
* interface language.

## `PRIVACY.md`

Owns:

* privacy policy;
* data processing;
* retention;
* data rights;
* detailed privacy practices.

## `TERMS.md`

Owns:

* legal terms;
* contractual conditions;
* legal responsibilities.

Do not duplicate the authoritative content of these documents here.

---

# 58. Final Design Review

Before approving the design system, verify:

### Product Alignment

* Does it simplify vacancy publishing?
* Does it simplify job discovery?
* Does it support selection processes?
* Does it preserve Radar's operational purpose?
* Does it support the subscription hypothesis without dark patterns?

### Human-washing Alignment

* Does it feel warm?
* Does it feel human?
* Does it avoid cold technology aesthetics?
* Does it remain professional?
* Is the human quality expressed through interaction rather than decoration?

### Accessibility

* Can the interface be operated by keyboard?
* Are states understandable without color?
* Are controls readable?
* Are touch targets usable?
* Does reduced motion work?

### Responsive Behavior

* Does Mural work on mobile?
* Does vacancy detail work on mobile?
* Does Radar work on mobile?
* Do forms work on mobile?
* Do filters work on mobile?
* Do subscription flows work on mobile?

### Simplicity

* Could any component be removed?
* Could any field be removed?
* Could any step be removed?
* Could any navigation item be removed?
* Could any visual effect be removed?

### Implementation

* Can a Django developer implement the system directly?
* Can an AI coding agent reproduce the patterns?
* Are tokens semantic?
* Are components reusable?
* Does the system remain compatible with Tailwind and Alpine.js?
* Does it avoid unnecessary custom CSS?

---

# 59. Final Principle

Simpel should not compete with traditional recruitment software by becoming a prettier version of traditional recruitment software.

It should feel fundamentally simpler.

The interface should consistently communicate:

> **People are not records.**
>
> **Recruitment is not bureaucracy.**
>
> **Technology should reduce friction, not create it.**

The visual system should therefore remain:

**Warm enough to feel human.**
**Structured enough to feel trustworthy.**
**Simple enough to feel effortless.**
**Professional enough to be taken seriously.**

The ultimate measure of the design is not how sophisticated it looks.

It is whether a Recruiter or Candidate can complete the next meaningful action with confidence and without unnecessary friction.

> **Simpel: technology that gets out of the way so people can focus on people.**

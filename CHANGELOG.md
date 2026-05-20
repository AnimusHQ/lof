# Changelog

All notable changes to **Life OS Framework** are recorded in this file.

This changelog is a production governance artifact, not a marketing feed. It exists to help users, maintainers, contributors, and AI-assisted workflows understand exactly what changed, why it changed, how risky the change is, and whether private vault owners need to migrate anything.

The project follows a structured release model inspired by semantic versioning and human-readable changelog conventions, adapted for a framework that includes documentation, schemas, templates, vault structure, AI policies, automation, security controls, and profession packs.

---

## Release Philosophy

Life OS Framework is not a normal application with one database and one deployment target.

It is a **framework repository** used to generate and maintain many private, user-owned vaults. That means release quality must be stricter than ordinary documentation projects:

- A schema change can affect dashboards, AI context packs, validation scripts, and migrations.
- A template change can affect user workflows and profession packs.
- A security policy change can alter what data may be stored or processed.
- An AI policy change can alter which actions are safe, draft-only, or forbidden.
- A sync or backup recommendation can affect recoverability.
- A profession pack update can affect real work in design, engineering, teaching, machining, healthcare study, legal work, consulting, finance, and other domains.

Therefore, every release must preserve the core promise of the framework:

> **A human-owned, local-first, secure, AI-augmented personal operating system that remains durable, understandable, recoverable, and adaptable over time.**

---

## What This Changelog Tracks

This changelog tracks changes to the shared framework repository, including:

- architecture contracts;
- data model contracts;
- security policy;
- AI agent model;
- sync, backup, and recovery guidance;
- installation workflows;
- vault structure;
- profession packs;
- automation policies;
- CI/CD validation;
- repository governance;
- migration instructions;
- release process;
- troubleshooting guidance;
- schemas;
- templates;
- examples;
- validation scripts;
- documentation structure;
- production claims and positioning.

This changelog does **not** track changes inside a user’s private vault unless those changes are part of a documented migration path from a framework release.

---

## Repository Boundary

The changelog covers the **shared framework repository** only.

It must never include:

- private personal notes;
- private financial data;
- private people or relationship notes;
- client-confidential data;
- patient data;
- student data;
- legal matter data;
- identity documents;
- passwords;
- API keys;
- private keys;
- seed phrases;
- raw AI memory dumps;
- raw calendar exports containing private events;
- unreviewed logs from personal systems.

If a release requires an example, the example must be synthetic, anonymized, and safe for public or internal repository distribution.

---

## Versioning Model

Life OS Framework uses version identifiers with the following intent:

```text
MAJOR.MINOR.PATCH[-PRERELEASE]
```

Examples:

```text
0.1.0-alpha.1
0.2.0
0.2.1
1.0.0
1.1.0
2.0.0
```

### Major Version

A major version indicates incompatible framework changes that may require explicit migration.

Examples:

- stable vault kernel change;
- breaking data model change;
- incompatible schema version;
- AI permission model change that alters safety assumptions;
- removal of supported installation profile;
- major security posture change;
- migration from one canonical metadata format to another.

### Minor Version

A minor version indicates compatible improvements that may require optional adoption steps.

Examples:

- new profession pack;
- new dashboard;
- new validation job;
- new template;
- new safe automation;
- new documentation section;
- new installation profile;
- new context pack type;
- non-breaking schema extension.

### Patch Version

A patch version indicates corrections and low-risk refinements.

Examples:

- typo fixes;
- clarified instructions;
- fixed broken internal links;
- improved examples;
- non-breaking validation fixes;
- documentation corrections;
- safer defaults that do not break existing users.

### Prerelease Version

Prerelease versions are used before production stability.

Examples:

```text
0.1.0-alpha.1
0.5.0-beta.1
1.0.0-rc.1
```

Prerelease versions may change more frequently and should not be treated as stable production contracts unless explicitly marked as release candidates.

---

## Stability Levels

Each release may include stability labels.

| Stability | Meaning | User Action |
|---|---|---|
| `experimental` | Exploratory; may change or be removed | Use only in test vaults |
| `draft-contract` | Written contract exists but may still change | Review before adoption |
| `candidate` | Intended for production after final validation | Test migration |
| `stable` | Production-supported | Safe default |
| `deprecated` | Supported temporarily; replacement exists | Plan migration |
| `removed` | No longer supported | Migration required |

---

## Change Categories

Each release entry uses the following categories.

### Added

New features, docs, schemas, templates, profession packs, workflows, automations, or validations.

### Changed

Behavioral, structural, or policy changes to existing components.

### Fixed

Corrections to broken, inconsistent, ambiguous, unsafe, or incomplete content.

### Security

Security-related changes, including threat model, forbidden data rules, AI policy, credential handling, incident response, and validation.

### AI Safety

Changes to Agent Gateway, context packs, AI action classes, draft/review workflow, MCP policy, RAG policy, semantic index policy, and evaluation requirements.

### Data Model

Changes to object types, required properties, relationships, statuses, IDs, sensitivity, provenance, retention, schema versioning, or migration.

### Vault

Changes to vault folders, folder contracts, dashboard locations, template locations, attachment policy, archive policy, or private vault layout.

### Sync / Backup / Recovery

Changes to live sync strategies, backup scope, restore drills, RPO/RTO, conflict handling, encrypted archives, key recovery, or recovery runbooks.

### Calendar / Notifications

Changes to calendar source-of-truth rules, reminders, review cadence, deadlines, meeting notes, time-blocking, notification tiers, or AI calendar boundaries.

### Profession Packs

Changes to profession pack rules, pack manifests, schemas, dashboards, templates, AI agents, review checklists, or supported roles.

### Automation / CI

Changes to validation jobs, GitHub Actions, local validation scripts, automation classes, workflow hardening, artifacts, logs, or release blockers.

### Documentation

Changes to docs that clarify usage, architecture, governance, installation, migration, troubleshooting, examples, or roadmap.

### Deprecated

Features, profiles, schemas, templates, or policies that remain available but should be replaced.

### Removed

Features, profiles, schemas, templates, or policies removed from the framework.

### Migration

Required or recommended migration steps for users and maintainers.

---

## Change Severity

Every meaningful change should be assigned a severity class.

| Severity | Meaning | Examples | Release Impact |
|---|---|---|---|
| `C0` | Editorial | Typos, formatting | No release block |
| `C1` | Clarification | Better explanation, examples | No release block |
| `C2` | Non-breaking extension | New optional field, template, pack | Minor or patch |
| `C3` | Behavioral change | Changed workflow, validation, default | Minor |
| `C4` | Compatibility-impacting | Schema, template, dashboard, AI policy impact | Minor or major |
| `C5` | Security-critical | Forbidden data, secrets, AI tool access, incident response | Immediate patch or security release |
| `C6` | Breaking change | Kernel, schema, migration, release policy break | Major or prerelease gate |

---

## Release Risk Labels

A release may carry one or more risk labels.

```text
risk:data-model
risk:security
risk:ai-policy
risk:sync
risk:backup
risk:calendar
risk:profession-pack
risk:migration
risk:automation
risk:ci
risk:governance
risk:documentation
```

Risk labels help users decide whether they must read the migration guide before adoption.

---

## Required Release Metadata

Every release entry must include:

```yaml
version:
date:
stability:
risk_labels:
compatibility:
migration_required:
security_review:
ai_safety_review:
data_model_review:
backup_restore_review:
release_owner:
```

Example:

```yaml
version: 0.4.0
date: 2026-05-19
stability: draft-contract
risk_labels:
  - risk:data-model
  - risk:migration
compatibility: non-breaking
migration_required: recommended
security_review: passed
ai_safety_review: passed
data_model_review: passed
backup_restore_review: not-applicable
release_owner: maintainers
```

---

## Migration Flags

Each release must clearly indicate user action.

| Flag | Meaning |
|---|---|
| `migration: none` | No user migration needed |
| `migration: optional` | Users may adopt improvements manually |
| `migration: recommended` | Users should adopt changes during next review |
| `migration: required` | Users must migrate to remain compatible |
| `migration: security-required` | Users should update immediately for security reasons |

---

## Compatibility Notes

Each release should state whether it affects:

- existing private vaults;
- schemas;
- templates;
- dashboards;
- profession packs;
- AI context packs;
- automation scripts;
- CI/CD;
- sync profiles;
- backup procedures;
- installation instructions;
- calendar workflows;
- security posture;
- migration process.

---

## Security Release Policy

Security changes must be easy to find.

A security release should include:

- affected files;
- affected versions;
- severity;
- impact;
- user action;
- maintainer action;
- whether private vaults are affected;
- whether secrets may have leaked;
- whether migration is required;
- whether AI permissions are affected;
- whether backup/restore is affected.

Security releases must not disclose exploit details before maintainers have had time to mitigate the issue.

---

## AI Safety Release Policy

AI-related changes must be reviewed carefully because they may alter the level of autonomy or the blast radius of a tool.

AI safety release notes must state whether the change affects:

- Agent Gateway;
- action classes;
- context pack schema;
- AI_Drafts;
- review queue;
- MCP tools;
- Local REST integration;
- semantic index;
- RAG retrieval;
- redaction;
- audit logs;
- human approval;
- external side effects;
- calendar mutations;
- repository mutations;
- sensitive data access.

No AI-related release may silently expand permissions.

---

## Data Model Release Policy

Data model changes must be explicit and migration-aware.

A data model release note must state:

- changed object types;
- changed required properties;
- changed optional properties;
- changed controlled vocabularies;
- changed sensitivity inheritance;
- changed relation model;
- changed folder mapping;
- changed validation rules;
- changed schema version;
- migration path;
- downgrade limitations.

---

## Profession Pack Release Policy

Profession packs are overlays, not forks of the framework.

Profession pack release notes must state:

- pack name;
- pack version;
- compatible framework versions;
- affected note types;
- affected templates;
- affected dashboards;
- affected checklists;
- affected AI agents;
- affected safety constraints;
- whether the pack is experimental, candidate, or stable.

Profession packs must not weaken security, AI, or data model rules.

---

## Release Entry Template

Use this template for every new release.

```markdown
## [VERSION] - YYYY-MM-DD

**Stability:** stable | candidate | draft-contract | experimental  
**Compatibility:** compatible | migration-recommended | migration-required | breaking  
**Migration:** none | optional | recommended | required | security-required  
**Risk labels:** risk:...  
**Release owner:** maintainers  

### Summary

Short human-readable summary of the release.

### Added

- ...

### Changed

- ...

### Fixed

- ...

### Security

- ...

### AI Safety

- ...

### Data Model

- ...

### Vault

- ...

### Sync / Backup / Recovery

- ...

### Calendar / Notifications

- ...

### Profession Packs

- ...

### Automation / CI

- ...

### Documentation

- ...

### Deprecated

- ...

### Removed

- ...

### Migration

- ...

### Compatibility Notes

- Existing private vaults:
- Schemas:
- Templates:
- Dashboards:
- AI context packs:
- Profession packs:
- Automation:
- CI/CD:
- Sync:
- Backup:
- Calendar:
- Security:

### Validation

- Markdown validation:
- Schema validation:
- Template validation:
- Profession pack validation:
- Security checks:
- AI safety checks:
- CI checks:
- Migration checks:
- Release review:

### Known Limitations

- ...

### Upgrade Guidance

- ...
```

---

## Changelog Maintenance Rules

Maintainers must follow these rules:

1. Every release must have a changelog entry.
2. Every breaking change must be visible in the release heading or migration section.
3. Security-impacting changes must be listed under `Security`.
4. AI-impacting changes must be listed under `AI Safety`.
5. Data model changes must be listed under `Data Model`.
6. Profession pack compatibility changes must be listed under `Profession Packs`.
7. Migration steps must never be hidden in prose only.
8. Private user data must never appear in the changelog.
9. Marketing claims must be accurate and scoped.
10. The changelog must be updated before release tagging.

---

## Changelog Quality Gates

A release cannot be marked production-ready unless the changelog entry includes:

```text
[ ] version
[ ] date
[ ] stability
[ ] compatibility
[ ] migration flag
[ ] release summary
[ ] security notes
[ ] AI safety notes
[ ] data model notes
[ ] migration notes
[ ] compatibility notes
[ ] validation summary
[ ] known limitations
[ ] upgrade guidance
```

---

## Premium Positioning Policy

Life OS Framework may use premium positioning when it reflects real engineering rigor.

Allowed:

- "production-grade";
- "local-first";
- "security-first";
- "AI-augmented";
- "human-owned";
- "schema-driven";
- "profession-adaptable";
- "recoverability-oriented";
- "designed for long-term durability";
- "built around explicit trust boundaries";
- "designed to support self-hosted and cloud workflows".

Not allowed:

- "perfectly secure";
- "unhackable";
- "guaranteed private";
- "fully autonomous without risk";
- "no need for backups";
- "AI can safely manage everything";
- "one tool replaces all calendars, task managers, financial systems, and security tools";
- "compliant by default with every law and industry regime".

The changelog must preserve trust by describing real changes, limitations, and user responsibilities.

---

## Current Release Status

The framework is currently in **pre-v1 production documentation phase**.

The following production contracts have been prepared:

```text
README.md
01_PROJECT_BRIEF.md
02_ARCHITECTURE.md
03_DATA_MODEL.md
04_SECURITY_MODEL.md
05_AI_AGENT_MODEL.md
06_SYNC_BACKUP_RECOVERY.md
07_INSTALLATION.md
08_VAULT_STRUCTURE.md
09_PROFESSION_PACKS.md
10_CALENDAR_NOTIFICATIONS.md
11_AUTOMATION_MODEL.md
12_CI_CD_VALIDATION.md
13_ROADMAP.md
14_DECISIONS_LOG.md
SECURITY.md
CONTRIBUTING.md
```

The following repository governance and operational documents remain part of the production documentation set:

```text
CHANGELOG.md
MIGRATION_GUIDE.md
RELEASE_PROCESS.md
GOVERNANCE.md
TROUBLESHOOTING.md
LOCAL_LLM.md
MCP_INTEGRATION.md
SEMANTIC_INDEX.md
SELF_HOSTED_REFERENCE_STACK.md
EXAMPLES.md
```

This changelog initializes the release-history contract for those documents.

---

## [0.1.0-alpha.1] - 2026-05-19

**Stability:** draft-contract  
**Compatibility:** initial framework baseline  
**Migration:** none  
**Risk labels:** `risk:documentation`, `risk:security`, `risk:ai-policy`, `risk:data-model`, `risk:backup`, `risk:governance`  
**Release owner:** maintainers  

### Summary

Initial production documentation baseline for Life OS Framework.

This release establishes the core identity of the project: a local-first, human-owned, AI-augmented personal operating system framework built around Obsidian, Markdown, structured metadata, private vaults, controlled AI collaboration, secure sync, restore-tested backups, and profession-adaptable overlays.

This release does not yet represent a full v1.0 implementation. It is the foundational contract layer that future templates, schemas, scripts, profession packs, and automation will follow.

### Added

- Added production-grade `README.md` as the main repository entry point.
- Added `01_PROJECT_BRIEF.md` defining vision, goals, non-goals, audiences, success criteria, scope, and claims policy.
- Added `02_ARCHITECTURE.md` defining system architecture, control plane/runtime plane split, vault architecture, AI gateway, sync/backup layers, profession overlays, and Mermaid diagrams.
- Added `03_DATA_MODEL.md` defining canonical data contract, ontology, required properties, relationships, statuses, sensitivity, context packs, and validation rules.
- Added `04_SECURITY_MODEL.md` defining threat model, trust boundaries, forbidden data, AI risks, repository controls, vault security, sync security, incident response, and security validation.
- Added `05_AI_AGENT_MODEL.md` defining Agent Gateway, context packs, AI action classes, prompt/RAG safety, MCP boundaries, audit logs, evaluations, and human review.
- Added `06_SYNC_BACKUP_RECOVERY.md` defining live sync, versioning, backups, RPO/RTO, restore tests, conflicts, device lifecycle, and disaster recovery.
- Added `07_INSTALLATION.md` defining installation profiles, setup flow, security preflight, plugin policy, sync/backup setup, AI enablement, profession packs, and validation.
- Added `08_VAULT_STRUCTURE.md` defining stable vault kernel, folder contracts, allowed and forbidden content, AI access, lifecycle, archive policy, and profession overlays.
- Added `09_PROFESSION_PACKS.md` defining profession pack manifests, extension rules, templates, dashboards, AI agents, quality criteria, safety rules, and compatibility.
- Added `10_CALENDAR_NOTIFICATIONS.md` defining calendar/reminder/task model, notification tiers, meeting notes, deadlines, time-blocking, AI calendar boundaries, and provider profiles.
- Added `11_AUTOMATION_MODEL.md` defining automation classes, permissions, registry, canonical mutation policy, validation, context generation, audit logs, and safe orchestration.
- Added `12_CI_CD_VALIDATION.md` defining validation planes, severity classes, quality gates, release blockers, branch protection assumptions, CI jobs, and artifacts.
- Added `13_ROADMAP.md` defining phased delivery, maturity levels, release gates, risk burn-down, migration strategy, governance roadmap, and v1.0 path.
- Added `14_DECISIONS_LOG.md` defining ADR structure, baseline architectural decisions, rejected alternatives, dependency map, review triggers, and decision lifecycle.
- Added `SECURITY.md` defining vulnerability reporting, supported versions, severity model, forbidden data, AI safety policy, incident response, and security checklists.
- Added `CONTRIBUTING.md` defining contributor workflow, contribution classes, PR requirements, review matrix, ADR requirements, pack contribution policy, and merge checklist.
- Added `CHANGELOG.md` as the production release-history contract.

### Changed

- Established the project as a **framework/reference architecture**, not a monolithic app and not a shared vault.
- Established the shared repository as a **template/framework repository** containing reusable contracts, templates, schemas, policies, examples, scripts, and documentation.
- Established each user’s private vault as the **runtime plane** and canonical owner of personal data.
- Established Obsidian as the primary human interface, not the only execution engine.
- Established external calendars/reminders as the source of truth for time-critical execution.
- Established AI as a controlled augmentation layer, not an autonomous owner of the user’s life or data.
- Established sync, versioning, backup, and recovery as separate operational capabilities.

### Fixed

- Eliminated ambiguity between:
  - sync and backup;
  - framework repository and private vault;
  - canonical notes and derived artifacts;
  - AI draft outputs and accepted canonical changes;
  - calendar execution and vault context;
  - profession overlays and framework forks.
- Clarified that premium positioning must be backed by real architecture and must not overpromise security, autonomy, compliance, or reliability.
- Clarified that AI writes must go to draft/review zones unless explicitly reviewed and accepted by a human.

### Security

- Established forbidden data policy for passwords, API keys, private keys, seed phrases, raw credentials, full card numbers, full identity documents, and unmanaged secrets.
- Established sensitivity levels and security zones.
- Established repository security baseline:
  - private-first defaults for user vault repositories;
  - protected branches for framework repository;
  - CODEOWNERS;
  - required review for sensitive paths;
  - secret scanning;
  - push protection;
  - dependency monitoring;
  - CI validation.
- Established incident response expectations for secret leaks, bad AI policy changes, unsafe automation, backup failure, provider compromise, and sensitive data exposure.
- Established human review as a security boundary for canonical changes and high-impact actions.

### AI Safety

- Established Agent Gateway as the required mediation layer for AI-assisted workflows.
- Established context packs as scoped, generated, provenance-aware, sensitivity-aware AI input bundles.
- Established action classes from read-only to forbidden.
- Established draft-first AI workflow:
  - retrieve;
  - analyze;
  - draft;
  - review;
  - accept;
  - apply;
  - audit.
- Established that AI must not get unrestricted write/delete access to canonical vault files.
- Established prompt injection, RAG poisoning, tool abuse, data exfiltration, and excessive autonomy as first-class threat categories.
- Established AI calendar, sync, backup, security, and repository actions as review-required or forbidden depending on impact.

### Data Model

- Established Markdown + YAML/Properties as canonical storage.
- Established canonical/derived/external/forbidden data separation.
- Established base ontology:
  - note;
  - area;
  - project;
  - task;
  - person;
  - meeting;
  - decision;
  - resource;
  - asset;
  - client;
  - work-order;
  - finance-record;
  - finance-decision;
  - daily-note;
  - weekly-review;
  - monthly-review;
  - ai-agent;
  - context-pack;
  - review;
  - experiment;
  - architecture-decision;
  - checklist;
  - process;
  - standard;
  - deliverable.
- Established required fields:
  - id;
  - type;
  - title;
  - status;
  - created;
  - updated;
  - sensitivity.
- Established relation model, provenance model, retention model, and migration strategy.

### Vault

- Established stable vault kernel:
  - `00_System`;
  - `01_Inbox`;
  - `02_Daily`;
  - `10_Areas`;
  - `20_Projects`;
  - `30_Knowledge`;
  - `40_Work`;
  - `50_Finance`;
  - `60_People`;
  - `70_AI`;
  - `80_Archive`;
  - `99_Attachments`.
- Established folder contracts, allowed note types, forbidden content, AI access, sync/backup implications, and lifecycle rules.
- Established `40_Work` as the primary profession overlay zone.
- Established `01_Inbox/AI_Drafts` and `70_AI/Agent_Logs` as the default AI output zones.
- Established import quarantine as the default posture for untrusted imports.

### Sync / Backup / Recovery

- Established one primary live sync method per vault.
- Established sync as separate from backup and recovery.
- Established supported sync profiles:
  - Obsidian Sync;
  - GitHub/Git;
  - Gitea/Forgejo;
  - Nextcloud;
  - Syncthing;
  - hybrid.
- Established encrypted local and offsite backups as production expectations.
- Established restore testing as mandatory for production readiness.
- Established RPO/RTO model and recovery runbooks.

### Calendar / Notifications

- Established external calendar/reminder systems as source of truth for critical time commitments.
- Established Obsidian as context, agenda, review, and meeting-note layer.
- Established notification tiers.
- Established meeting note, event note, deadline, waiting-for, and review contracts.
- Established AI calendar actions as constrained and approval-aware.

### Profession Packs

- Established profession packs as overlay extensions, not forks.
- Established `pack.yaml` manifest model.
- Established baseline profession domains:
  - developer;
  - designer;
  - machinist / craftsperson;
  - teacher;
  - researcher;
  - founder / operator;
  - lawyer / legal;
  - healthcare study;
  - finance;
  - student;
  - writer / creator;
  - artist / creative;
  - consultant.
- Established pack compatibility, validation, safety, migration, and review rules.

### Automation / CI

- Established automation classes and action boundaries.
- Established canonical mutation policy.
- Established validation workflow for:
  - Markdown;
  - frontmatter;
  - schemas;
  - templates;
  - profession packs;
  - Mermaid diagrams;
  - links;
  - secrets;
  - AI policies;
  - automation policies;
  - migration files;
  - release entries.
- Established release blockers and warning-only checks.
- Established CI/CD as the production immune system of the framework.

### Documentation

- Added the complete P0 documentation foundation.
- Established documentation dependency order:
  - brief;
  - ADRs;
  - architecture;
  - data model;
  - security;
  - AI;
  - sync/recovery;
  - installation;
  - vault structure;
  - profession packs;
  - calendar;
  - automation;
  - CI/CD;
  - roadmap;
  - README;
  - security policy;
  - contribution policy;
  - changelog.
- Established copy-ready repository documentation style.
- Established documentation claims policy.

### Deprecated

- Deprecated any approach that treats Obsidian as the only source of critical reminders.
- Deprecated the idea of a shared team vault containing personal private data.
- Deprecated unrestricted AI access to the canonical vault.
- Deprecated using sync as a backup strategy.
- Deprecated storing secrets or raw credentials in Markdown.
- Deprecated profession-specific forks that modify the stable vault kernel.
- Deprecated manual-only governance for schemas, templates, security policy, and AI policy once CI validation is available.

### Removed

- Removed the assumption that GitHub is the only viable storage option.
- Removed the assumption that all users must be developers.
- Removed the assumption that AI should directly edit canonical notes.
- Removed the assumption that calendar data should live primarily inside Obsidian.
- Removed the assumption that one tool should replace all external execution systems.

### Migration

No migration is required because this is the initial documentation baseline.

Users creating early private vaults from this baseline should treat all contracts as draft-contract until the framework reaches a stable release candidate.

Recommended adoption steps:

1. Read `README.md`.
2. Read `01_PROJECT_BRIEF.md`.
3. Read `14_DECISIONS_LOG.md`.
4. Read `02_ARCHITECTURE.md`.
5. Read `03_DATA_MODEL.md`.
6. Read `04_SECURITY_MODEL.md`.
7. Read `05_AI_AGENT_MODEL.md`.
8. Select an installation profile from `07_INSTALLATION.md`.
9. Configure sync and backup using `06_SYNC_BACKUP_RECOVERY.md`.
10. Validate vault structure using `08_VAULT_STRUCTURE.md`.
11. Select or create profession packs using `09_PROFESSION_PACKS.md`.
12. Configure calendar/reminder workflow using `10_CALENDAR_NOTIFICATIONS.md`.

### Compatibility Notes

- Existing private vaults: not applicable.
- Schemas: draft baseline established.
- Templates: draft baseline established.
- Dashboards: draft baseline established.
- AI context packs: draft baseline established.
- Profession packs: draft baseline established.
- Automation: policy baseline established.
- CI/CD: validation baseline established.
- Sync: supported profiles defined.
- Backup: restore-tested model defined.
- Calendar: source-of-truth model defined.
- Security: baseline policy established.

### Validation

The following validations were applied to generated documentation artifacts:

- Markdown code fences balanced.
- No known placeholder markers in generated files.
- Major architecture documents include dependency alignment.
- Security and AI boundaries are explicitly documented.
- Documentation references stable framework principles.
- Files are copy-ready for repository use.

Full automated CI validation is not yet implemented in this release. It is specified in `12_CI_CD_VALIDATION.md` and remains part of the implementation roadmap.

### Known Limitations

- Framework repository structure is specified but not yet fully generated as an installable repository tree.
- JSON schemas are specified conceptually but not yet fully implemented as machine-validated files.
- Validation scripts are specified conceptually but not yet implemented.
- Profession pack examples are specified in documentation but not yet packaged as installable pack directories.
- Agent Gateway is specified architecturally but not yet implemented.
- Semantic index and MCP integration remain future layers.
- Self-hosted reference stack remains documentation-level until `SELF_HOSTED_REFERENCE_STACK.md` is produced.
- Migration guide, release process, governance, and troubleshooting documents remain to be authored after this changelog.

### Upgrade Guidance

No upgrade action is needed for users because this is the initial baseline.

For maintainers, the next recommended documents are:

```text
MIGRATION_GUIDE.md
RELEASE_PROCESS.md
GOVERNANCE.md
TROUBLESHOOTING.md
LOCAL_LLM.md
MCP_INTEGRATION.md
SEMANTIC_INDEX.md
SELF_HOSTED_REFERENCE_STACK.md
EXAMPLES.md
```

---

## Pre-Release Workstream Log

This section records the production documentation workstream leading to `0.1.0-alpha.1`.

### Documentation Contracts Prepared

```text
01_PROJECT_BRIEF.md
14_DECISIONS_LOG.md
02_ARCHITECTURE.md
03_DATA_MODEL.md
04_SECURITY_MODEL.md
05_AI_AGENT_MODEL.md
06_SYNC_BACKUP_RECOVERY.md
07_INSTALLATION.md
08_VAULT_STRUCTURE.md
09_PROFESSION_PACKS.md
10_CALENDAR_NOTIFICATIONS.md
11_AUTOMATION_MODEL.md
12_CI_CD_VALIDATION.md
13_ROADMAP.md
README.md
SECURITY.md
CONTRIBUTING.md
CHANGELOG.md
```

### Baseline Decisions Established

- Framework-first, not app-first.
- Template repo, not shared personal vault.
- Private canonical vault per user.
- Markdown + YAML/Properties as canonical storage.
- Derived dashboards and context packs.
- External calendars for time-critical execution.
- Sync separate from backup.
- Restore-tested backup required.
- AI mediated through Agent Gateway.
- AI writes to drafts, not canonical notes by default.
- Profession packs as overlays.
- Secrets forbidden in vault/repo.
- Governance through ADRs, CI, security review, and changelog.

---

## Future Release Skeleton

### [0.2.0] Framework Repository Skeleton

Expected focus:

- create repository folders;
- add vault-template skeleton;
- add docs folder structure;
- add schema folder structure;
- add templates folder structure;
- add policies folder structure;
- add profession-packs folder structure;
- add automation folder structure;
- add examples folder structure;
- add test folder structure;
- add `.github/workflows`.

### [0.3.0] Schema and Template Baseline

Expected focus:

- implement JSON schemas;
- implement Markdown templates;
- validate frontmatter;
- add template tests;
- add sample notes;
- add migration notes for schema adoption.

### [0.4.0] Security and CI Baseline

Expected focus:

- implement secret checks;
- implement Markdown validation;
- implement schema validation;
- implement profession-pack validation;
- implement Mermaid validation;
- implement CI artifacts;
- enable repository security controls.

### [0.5.0] Profession Pack Baseline

Expected focus:

- package developer pack;
- package designer pack;
- package machinist/craftsperson pack;
- package teacher pack;
- package researcher pack;
- package founder/operator pack;
- package custom pack template.

### [0.6.0] Installation and Migration Baseline

Expected focus:

- provide bootstrap scripts;
- provide installation checklists;
- provide migration guide;
- provide release process;
- provide troubleshooting guide.

### [0.7.0] AI Context Pack Baseline

Expected focus:

- define context pack generator;
- define AI draft validator;
- define audit log format;
- define semantic index policy;
- define MCP integration policy.

### [0.8.0] Automation Baseline

Expected focus:

- implement validation CLI;
- implement health report generator;
- implement backup manifest generator;
- implement local runner;
- implement CI parity checks.

### [0.9.0] Production Candidate

Expected focus:

- end-to-end validation;
- documentation polish;
- example vaults;
- migration dry-runs;
- security review;
- AI safety review;
- restore drill validation;
- beta user feedback.

### [1.0.0] Production Release

Expected focus:

- stable contracts;
- stable vault kernel;
- stable data model;
- stable installation profiles;
- stable security policy;
- stable AI action classes;
- stable profession pack format;
- stable CI validation;
- documented migration path;
- release notes and known limitations.

---

## Maintainer Notes

Before cutting any release, maintainers should ask:

```text
[ ] Does the changelog accurately describe the release?
[ ] Are breaking changes clearly visible?
[ ] Are migration steps explicit?
[ ] Are security implications documented?
[ ] Are AI implications documented?
[ ] Are data model changes documented?
[ ] Are profession pack compatibility notes included?
[ ] Are known limitations honest?
[ ] Are claims accurate?
[ ] Are release blockers resolved?
[ ] Are validation results available?
```

---

## Release Integrity Statement

A Life OS Framework release is trustworthy only when users can understand:

- what changed;
- why it changed;
- whether they need to act;
- whether their private vaults are affected;
- whether security assumptions changed;
- whether AI permissions changed;
- whether schemas or templates changed;
- whether migration is required;
- whether recovery procedures changed;
- what limitations remain.

This changelog exists to make that understanding durable.

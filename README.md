AI CV Maker

A mobile-first workspace for building, improving, and tailoring professional CVs.

AI CV Maker is an independently developed mobile application that brings structured CV editing, AI assistance, job targeting, cover letters, templates, and document export into a unified workspace.

The project is built around a simple principle: your real experience remains the source of truth.

Users can start with a blank document, follow guided questions, or use AI to organize their professional story. Each approach leads into the same workspace, where the user retains control over the content and decides which changes to accept.

Status: Active development toward Premium V1. The core local application is implemented; live service integration, native device verification, and store release preparation remain in progress.

The Vision

Creating a CV means making decisions about how to present your experience, what information matters, and how to communicate it clearly for a particular opportunity.

AI CV Maker is designed to support that entire process.

The long-term product direction is a professional workspace where users can maintain their career information, improve its presentation, tailor applications, and reuse their work without starting from scratch every time.

Premium V1 focuses on:

Creating and editing structured CVs.
Helping users organize their professional experience.
Reviewing document completeness, consistency, and readability.
Proposing AI-assisted improvements.
Adapting content to specific job opportunities.
Creating cover letters grounded in the same professional information.
Applying templates and exporting professional documents.
Preserving work through local storage and planned cloud synchronization.
Core Principles
Never manufacture a career

AI should help users express what they have actually done.

The intended behavior is to clarify, organize, rewrite, and suggest improvements without inventing employers, qualifications, dates, achievements, or performance metrics.

This principle informs the AI contracts, validation rules, and proposal workflow. Live provider behavior remains part of release validation.

AI proposes. Domain validates. User decides.

AI-generated content enters the application through structured proposals.

Those proposals pass through validation and are presented for review. Accepted changes are applied through the same document commands used by the application.

The user remains responsible for the final content.

Local-first creation

The core writing experience should be useful before an account, purchase, or cloud connection is required.

Users can begin creating and editing locally. Cloud services, remote AI, and purchases have their own access and connectivity requirements.

One canonical document

A structured Resume Domain sits at the center of the application.

The editor, preview, templates, AI context, export pipeline, and synchronization payloads derive from this shared document model.

Three Ways to Start
Blank Canvas

For users who already know what they want to write.

Blank Canvas creates an editable CV that can be built directly through the manual editor.

Questionnaire

For users who benefit from guided questions.

The questionnaire is designed to help collect professional information and organize it into the CV structure. Its local implementation is in progress, with completion and polish still required.

AI Draft Studio

For users who want assistance turning their real professional story into a first draft.

The local flow includes generation handling, validation, and acceptance checks. Verification against the live AI provider remains a release milestone.

The Resume Workspace

The workspace centers the experience on the document itself.

Its existing components include:

A dashboard for managing local CV projects.
A domain-backed manual editor.
A central CV paper preview.
Template selection and local ownership logic.
Deterministic document review.
AI proposal previews and acceptance controls.
Local AI session history.
Job-targeting workflows.
Cover-letter foundations.
Export preparation and native sharing integration.

These systems are being brought together into a consistent mobile experience, with final device and visual QA still pending.

Resume Check and Job Targeting

Resume Check provides deterministic local guidance across areas such as:

Missing information.
Document completeness.
Structural consistency.
Content quality.
Practical ATS considerations.

Job Targeting extends this with stored job targets, keyword matching, and local analysis.

The intended workflow helps users identify relevant experience and improve its presentation for a particular role. Real-provider AI suggestions remain under development and verification.

ATS guidance is intended to improve document structure and usability. The application does not promise guaranteed results from recruitment systems.

AI Assistance

AI is integrated through dedicated services and structured contracts.

The existing local architecture includes:

Context preparation from the current CV.
Provider abstraction.
Structured response handling.
Proposed-change validation.
Preview and acceptance checks.
Local session history.
Controlled application of accepted changes.

The intended service path connects the mobile application to a Supabase Edge Function, which handles communication with the external AI provider.

Local mock-handler checks have passed. Live OpenAI execution remains to be verified.

Cover Letters

Cover letters are part of the Premium V1 launch scope.

The implementation includes a dedicated document model, generation validation, local storage, and PDF preparation/export logic.

The goal is to create cover letters that remain consistent with the user’s real CV information and the opportunity they are targeting.

End-to-end provider, commercial, and native behavior still require validation.

Templates, Import, and Export
Templates

The application includes a registry of free and premium templates, together with local template-unlock storage.

The commercial design distinguishes permanent template ownership from temporary access through an active Pro plan.

Cross-device ownership reconciliation remains part of the external integration work.

Import

Existing import work supports TXT and pasted text.

PDF, DOC, and DOCX extraction remain planned capabilities and are not currently presented as completed features.

Export

The export pipeline transforms structured CV data into a document representation, prepares HTML output, and integrates with Expo Print and Expo Sharing.

Existing work covers document preparation, filenames, quality checks, and native runtime guards.

Final PDF rendering, sharing, and layout fidelity still require validation on devices.

Architecture

AI CV Maker uses a domain-first architecture with distinct responsibilities across its major systems.

Resume Domain

Defines the canonical CV structure through types, commands, reducers, and rules.

Feature Modules

Organize creation flows, workspace editing, AI assistance, templates, import/export, job targeting, cover letters, and settings.

Local Rule Engine

Provides deterministic review without requiring an AI request.

AI Services and Validators

Prepare context, communicate through provider boundaries, validate results, and expose reviewable proposals.

Persistence and Synchronization

Handle local document storage and provide integration boundaries for cloud synchronization.

Commercial Systems

Manage account capabilities, credits, paid access, template ownership, and Frozen Pro behavior separately from document content.

Rendering and Export

Project the CV into its visual representation and prepare document output.

This separation allows the application to evolve while maintaining a consistent source of truth for the user’s work.

Technology Stack

The September 2026 development snapshot includes:

React Native 0.81.5 — mobile application framework.
Expo SDK 54 — application tooling and native capabilities.
React 19.1.0 — component architecture.
TypeScript 5.9 — typed application and domain logic.
Expo Router 6 — navigation and routing.
AsyncStorage and Expo SQLite — local persistence.
Expo Print and Expo Sharing — document output and sharing.
Supabase JS — cloud integration.
Supabase migrations and Edge Functions — backend preparation and server-side AI boundary.
OpenAI adapter and local mock runtime — AI provider infrastructure.
Vitest 4 — automated testing.
EAS configuration — preview and production build preparation.

RevenueCat is the current billing candidate. Sandbox and entitlement planning exist; its SDK and live payment flows are not yet integrated.

Visual Identity

The interface separates workspace appearance from document presentation.

The surrounding application can use its own themes, while the CV remains a clean, white document surface.

The design direction includes:

Dark, Light, and Cream themes.
A document-centered workspace.
Contextual editing tools.
Consistent theme tokens.
Persisted appearance preferences.
Motion for important transitions.
The PaperSpawn animation as a recognizable product moment.

PaperSpawn and its replay controls are implemented. Final theme coverage, motion quality, and native performance remain subject to device testing.

Commercial Model

The product defines four account states:

Guest

Local CV creation and manual editing without an account.

Guest usage does not include AI or cloud access.

Free

Account-based capabilities with bounded credit refills and credit-based access to eligible premium operations.

The intended à la carte model lets users access specific capabilities without purchasing a Pro period.

Pro

Prepaid access for fixed periods, planned without automatic renewal at launch.

The model includes premium template access, clean exports, and a finite AI allowance.

Frozen Pro

A paused state designed to preserve remaining paid time and user data while productive Pro usage is suspended.

The commercial architecture keeps several concepts separate:

Recurring credit allowances.
Purchased credits, which are intended not to expire.
Temporary Pro access.
Permanent template ownership.
Credit-based clean exports for Free users.
Included clean exports for active Pro users.

Local entitlement and credit logic exist. Purchase verification, restoration, refunds, revocation, and backend reconciliation remain integration milestones.

Final pricing and availability will be established before launch.

How the Project Is Being Built

AI CV Maker is an independent project created by Alex Ionescu, using an AI-assisted development workflow with ChatGPT and Codex.

The work combines product planning, interaction design, architectural decisions, implementation, testing, and iterative refinement.

Development is organized around four distinct sources of truth:

Product Blueprint: the intended launch experience.
Current-State Audit: what the codebase actually contains.
Gap Analysis: what remains incomplete or unverified.
Implementation Plan: the order in which that work is addressed.

Changes are developed in focused batches, with checks across document behavior, architectural boundaries, AI contracts, commercial states, and persistence.

Quality and Verification

The repository report dated September 23, 2026 records:

Successful TypeScript verification.
699 passing tests across 153 test files.
Passing local AI Edge mock-handler and missing-key checks.
Successfully resolved Android and iOS application configurations.

The test suite covers areas including:

Resume Domain behavior.
Architectural boundaries.
AI proposal validation.
Import and export readiness.
Commercial account states.
Credit ledger behavior.
Local readiness contracts.

Native device behavior and live external integrations remain separate verification tasks.

Dependency security work is ongoing. Recorded triage removed critical advisories, while remaining high and moderate advisories require further upgrade assessment.

Road to Launch

The next milestones toward Premium V1 are:

Verify Supabase authentication, database policies, ownership, and synchronization.
Validate live AI requests through the server-side provider boundary.
Integrate and test billing, restoration, refunds, and entitlement reconciliation.
Complete Android and iOS runtime testing.
Verify persistence, export, sharing, and recovery on devices.
Complete questionnaire polish and visual QA.
Address outstanding dependency security work.
Finalize privacy documents, support information, account deletion behavior, and store materials.

Additional language coverage and broader document-import support remain part of the product direction.

Creator

Alex Ionescu
Independent software and AI builder
Bucharest, Romania

GitHub: https://github.com/rotici

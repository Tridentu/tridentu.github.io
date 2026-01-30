---
title: TRidentu 2 Live ISO (TRLIS) Specification
home: true
layout: default
---
# Software Requirements Specification
## For TRidentu 2 Live ISO (TRLIS)

Version 1.0  
Prepared by Aerodos12 
Tridentu Group
Monday January 26th, 2026

## Table of Contents
<!-- TOC -->
* [1. Introduction](#1-introduction)
    * [1.1 Document Purpose](#11-document-purpose)
    * [1.2 Product Scope](#12-product-scope)
    * [1.3 Definitions, Acronyms, and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    * [1.4 References](#14-references)
    * [1.5 Document Overview](#15-document-overview)
* [2. Product Overview](#2-product-overview)
    * [2.1 Product Perspective](#21-product-perspective)
    * [2.2 Product Functions](#22-product-functions)
    * [2.3 Product Constraints](#23-product-constraints)
    * [2.4 User Characteristics](#24-user-characteristics)
    * [2.5 Assumptions and Dependencies](#25-assumptions-and-dependencies)
    * [2.6 Apportioning of Requirements](#26-apportioning-of-requirements)
* [3. Requirements](#3-requirements)
    * [3.1 External Interfaces](#31-external-interfaces)
    * [3.2 Functional](#32-functional)
    * [3.3 Quality of Service](#33-quality-of-service)
    * [3.4 Compliance](#34-compliance)
    * [3.5 Design and Implementation](#35-design-and-implementation)
    * [3.6 AI/ML](#36-aiml)
* [4. Verification](#4-verification)
* [5. Appendixes](#5-appendixes)
<!-- TOC -->

## Revision History

| Name | Date | Reason For Changes | Version |
|------|------|--------------------|---------|
|      |      |                    |         |
|      |      |                    |         |

## 1. Introduction
➥ Briefly summarize the SRS’s purpose, product scope, intended audience, and how the document is organized. Do not include details here; reference the relevant sections instead.

This document is meant for detailing and explaining the style and requirements for building a proper Tridentu 2 ISO-based system. The TRLIS standard will cover both the installed system and the ISO version as well. This document is **ALWAYS** meant for anyone (developers, engineers and end-users) to read and eventually understand. 

### 1.1 Document Purpose

The TRidentu Live ISO Specification (or TRLIS) is a set of rules (a.k.a style guide, like PEP 8) that details how the Tridentu ISO is to be built as well as how its contents are to be installed/managed. This specification/style guide is meant for engineers/developers (for Contributions) and end-users (to understand their system at a deeper level).

### 1.2 Product Scope

Tridentu 2 (via TRLIS) uses a "release-code" system that defines **3 MAJOR** components:

1. The UI environment used (i.e CT for Linux Console, K for KDE, etc.)
2. Purpose (Optional Component that defines best/dominant use case - i.e. KG for Gaming via KDE)
3. Version Number (i.e 1.5)


Tridentu 2 is mainly a Linux distro with influences from other systems (such as BSD) considered. The CT version is **ALWAYS** the baseline, so most of those critical standards found in that will be listed here. anything with K or G as the first letter (except in GT) are usually desktop environments. Anything after that defines capabilities by purpose (i.e. KG would support gaming and come with WINE pre-installed). The goal of all this is to standardize and streamline a new ISO production pipeline that allows for flexible upgrades/releases.


### 1.3 Definitions, Acronyms, and Abbreviations

💡 Tips:
- Include terms that impact interpretation of requirements (e.g., “user,” “tenant,” “near real-time”).
- Keep entries alphabetized and consistent across the document set.

| Term  | Definition                                                                                                                                          |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| API   | Application Programming Interface - A set of definitions and protocols for building and integrating application software                            |
| BTRFS | B-TRee FS - A filesystem that a modern, copy-on-write (CoW) filesystem for Linux designed for advanced storage, high capacity, and data integrity.  |
| CT    | Console Terminal - A variant of Tridentu 2 (1.5+) that only uses the Linux console. It is also the smallest variant to be commissioned for creation/official use. |
| DE    | Desktop Environment - A complete graphical interface (GUI) that provides a user-friendly way to interact with an operating system.                  |
| SRS   | Software Requirements Specification - A document that describes the intended purpose, requirements, and nature of a software                        |
| TR2RC | TRidentu 2 Release Code - a 3-part set of letters and numbers that define the UI environment, purpose and/or version of the distro                  |
| TRLIS | TRidentu 2 Live ISO Specification - A set of rules and standards that keep Tridentu 2's development from stalling                                   |
| UI    | User Interface - The visual part of computer application through which a user interacts with a software                                             |
| WINE  | WINE - A Windows Emulation layer that only comes on Gaming-based variants of Tridentu 2.                                                            |

### 1.4 References

➥ Cite standards, contracts, policies, interface specs, UX style guides, use-case docs, architectural decisions, or a vision/scope document. For each reference, include title, author/owner, version, date, and location/URL. Indicate whether each reference is normative (binding) or informative (guidance).

Most References will be listed below from this document. The reason for that is due to the fact that the standards come directly from here. Anything else will have a page linked to it.

1. G. Beekmans, *Linux From Scratch*. Linux From Scratch. [Online]. Available: [https://www.linuxfromscratch.org/lfs/view/stable-systemd/index.html](https://www.linuxfromscratch.org/lfs/view/stable-systemd/index.html). Accessed: Jan. 26, 2026.
2. Mina[@yes_i_cane], "Understanding Braille Notetakers for Blind Users," TikTok, Jun. 17, 2025. Available: [https://www.tiktok.com/@yes_i_cane/video/7517025924278160695](https://www.tiktok.com/@yes_i_cane/video/7517025924278160695) [Accessed: Jan. 26, 2026] [Online Video]

The following references are normative:
 
 - Reference #1
 - Reference #2

### 1.5 Document Overview

- The overview section focuses on how everything in this document comes together regarding requirements.
- The perspective section focuses on the history/vision being Tridentu 2
- The functions section focuses on the main objectives of each planned/available Tridentu 2 variant
- The constraints section focuses on what is and is not allowed regarding build the distro.


## 2. Product Overview

### 2.1 Product Perspective
Tridentu 2 was created mainly to learn about how Linux systems such as Fedora, Arch, Debian and Gentoo are built/created. as a result, this system follows most if not all instructions to the letter in Linux From Scratch.

### 2.2 Product Functions

Tridentu 2 as a Linux distribution provides the following:

- Enhanced use of GNU/Linux out of the box, **ESPECIALLY** on graphical or DE versions.
- Support for various file systems (including BTRFS)
- Networking Support
- TUI Installer for **ALL VERSIONS**
- Package Management for optional programs and libraries.
- Advanced, yet convenient system management (whether via dkms, zram-generator or even genfstab).



### 2.3 Product Constraints

Each constraint is coded by C followed by a number. It is also prefixed with "TRLIS". All constraints below **(unless otherwise stated)** are *BOTH INTERNAL AND EXTERNAL*.

- TRLIS-C01: **ALL** Tridentu 2 systems *MUST* have Systemd as the default init system due to constraints on the others regard the DE variants (i,e. GNOME, KDE, etc.). Other init systems **may** be packaged using either Caravel **OR** dpkg. This is *MANDATORY*.
- TRLIS-C02: **EVERY** version of Tridentu 2 *MUST* start out with a CT (or Linux Console/Console-Terminal) variant. it is usually marked as CT-{version} and can hold the following variants of itself:
  - CTS (Server Edition)
  - CTD (Derivative/Developer Edition)
  This is *MANDATORY*.
- TRLIS-C03: Accessibility Sofware/Systems *MUST* be provided for every version's CT variant. This also carries over to **ANY** derivative variant of CT (even without the letters). This is *MANDATORY*.
- TRLIS-C04: NetworkManager *MUST* come with the CT variant. For security reasons, this is *MANDATORY*.
- TRLIS-C05: Per TRLIS-C03, Bluetooth *MUST* **ALSO** be supported. This is to support **ANY** Braille reader/writer that uses Bluetooth. This is *MANDATORY*.
- TRLIS-C06: DKMS *MUST* be pre-installed. This is to adhere to the "advanced, yet convenient" principle of the Tridentu 2 Philosophy. This is *MANDATORY*.
- TRLIS-C07: Power awareness (power management usage being key) is a *MUST* on the baseline CT system. This means that programs such as power-profiles-daemon are to be preinstalled **EVERYWHERE**. This is *MANDATORY*.
- TRLIS-C08: The shell on the *user* (no root) side *MUST* be friendly to said user. Unless **HEAVILY** modified for ease of use, Bash is **NOT** acceptable as such a shell. Fish is disqualified also from this due to the lack of POSIX compliance. This is *MANDATORY*.
- TRLIS-C09: The system shell (underlying **AND** root-based) should ALWAYS be bash. This is *MANDATORY*.
- TRLIS-C10: Development tools necessary for the baseline (CT) *MUST* remain on the system if it is deemed "useful" for the end user in education (STEM education, specifically). Examples include GCC, Ruby, Python, LLVM, Git, etc. This is *CONDITIONALLY MANDATORY* (depends on the software in question).
- TRLIS-C11: All variants of the distribution *MUST* use dracut as the starting initramfs. Also, the absence of an initramfs system is **STRICTLY PROHIBITED**. Alternatives can be packaged for optional use, but this is *MANDATORY*.
- TRLIS-C12: There should be a font that is readable and unique to the distribution. This is *PREFERRED*.
- TRLIS-C13: There *MUST* always be i386 BIOS modules present for use with GRUB. This is *MANDATORY*.
- TRLIS-C14: There *MUST* always be Linux-PAM present and in use with shadow as the main security/authentication system. This is *MANDATORY*.
- TRLIS-C15: All variants and derivatives *MUST* come with some sort of web browser. This is *MANDATORY*.
- TRLIS-C16: All variants and derivatives *MUST* support FUSE (Filesystem in USERspace). This is *MANDATORY*.
- TRLIS-C17: All variants *MUST* have Systemd built with sysusers support. This is *MANDATORY*.
- TRLIS-C18: All variants *MUST* be capable of fetch SSL sertificates. This is *MANDATORY*.
- TRLIS-C19: All variants *MUST* be ISO'd with autologin enabled on the following programs:
    1. sudo
    2. Linux console login
This is *MANDATORY*.
- TRLIS-C20: Certain files (such as Squash Images) *MUST* be viewable on any variant/derivative. This is *MANDATORY*.
- TRLIS-C21:  The directories  ```/usr/lib64```, ```/usr/libx32``` and ```/opt/lib``` *MUST*  be included in every Tridentu 2 variant/derivative. This is (for compatibility reasons) *MANDATORY* . 
- TRLIS-C22: The .zshrc file in /etc/skel *MUST* accomodate dealing with Xorg compilation. The same goes for the tridentulive user. This is *MANDATORY* 
- TRLIS-C23: **NOTHING** belongs in /usr/lib64 *unless* specified. This is to avoid serious confusion regarding the installation of neccessary packages. This is *MANDATORY*.
- TRLIS-C24: Intel support for GPUs is **ESSENTIAL**. This is mainly due to the origin point of Tridentu 2, but is also good precend for other GPU brands as well. This is *CONDITIONALLY MANDATORY* (Only time it can be disobey is due to severe obsolescence).
- TRLIS-C25: Nouveau (NVIDIA) support *MUST* also be present. This is a reciprocal constraint, so this is *ABSOLUTELY MANDATORY*.
- TRLIS-C26: Any third-party codecs governed under patents *MUST* be removed from **ALL** graphical distribution variants. To avoid legal trouble per the LFS Book, this is *ABSOLUTELY MANDATORY*
- TRLIS-C27: A font collection *MUST* be present for **ALL** graphical variants of the Tridentu 2 Linux distribution. This is to ensure versatility regarding the look and feel, documents, terminal/coding use and self-expression. This is *MANDATORY* **(for Graphical variants only)**.
- TRLIS-C28: All possible inputs *MUST* be supported. This is *ABSOLUTELY MANDATORY*.
- TRLIS-C29: Any groups needed for certain programs to function *MUST* be alloted to the superusers. This is *ABSOLUTELY MANDATORY*.
- TRLIS-C30: The default font for graphical variants *MUST* be either Cabin or similar fonts by function (UI only). *This is CONDITIONALLY MANDATORY*.
- TRLIS-C31: The default icon theme for graphical variants *MUST* be Papirus. Other themes but the Tridentu default can use other icon themes. This is *MANDATORY*. 

### 2.4 User Characteristics
💬 _Defines the user groups and the attributes that affect requirements._

There are mainly 3 types of Tridentu 2 users that are intended.

#### 2.4.1 The College Student

This user cares about two main things:
1. Accuracy
2. Productivity

Accuracy implies that the College Student wants to turn in assignments properly, with integiry **AND** on time. The main reason why Chrony is used instead of systemd-timesyncd is to prevent issues where timezone differences may interfere (cush as submitting an assignment to a professor).

Productivity is obvious - the College student wants to be able to use Tridentu 2 (or *ANY* distro following the Tridentu 2 Philosophy) in a way that can help them learn and succeed in school.

#### 2.4.2 The Dev(eloper)

This user cares about development of programs. They want to ensure that they can plan and even jump into coding almost immediately. To cater to this specific user, the Tridentu 2 distro comes with *various* development tools and languages builtin to the system when installed. One of those is GCC.

### 2.5 Assumptions and Dependencies
💬 _External assumed factors or conditions, as opposed to known facts, that the project relies on._

➥ List assumptions about environment, hardware, usage patterns, third-party components/services, and organizational support. List dependencies on external systems, libraries, or teams. For each, indicate potential impact if proven false.

💡 Tips:
- Link assumptions to risk register with owner and mitigation when available.

### 2.6 Apportioning of Requirements
💬 _Allocation of requirements across components or increments._

➥ Map major requirements to subsystems, services, or releases/iterations. Use a cross-reference table to show allocation and to clearly identify deferred requirements.

💡 Tips:
- Note unknown allocations explicitly and track as follow-ups.

## 3. Requirements
💬 _This section specifies **verifiable** requirements of the software product to enable design and testing._

➥ State requirements to a level of detail sufficient for design and verification. Use unique identifiers, consistent keywords (shall/should/may), and clear conditions. Describe inputs, processing in response, and outputs where applicable. Reference the relevant 2.3 Product Constraints that the requirement addresses.

📃 Template (applies to **all** requirements):
```markdown
- ID: REQ-FUNC-001
- Title: Short title, representative of the requirement...
- Statement: The system shall...
- Rationale: ...
- Acceptance Criteria: ...
- Verification Method: Test | Analysis | Inspection | Demonstration | Other
- More Information: Additional context. Links to related artifacts.
```
### 3.1 All Constraints Met

- ID: REQ-CONS-001
- Title: All Constraints Met
- Statement: The system shall meet the above constraints with ease. Failure to meet these requirements can result in the system being deemed inadequate.
- Rationale: The constraints above provided a basis for what is expect of the baseline version and many others.
- Acceptance Criteria: All constraints shall be checked off in written form for every version greater than 1.5
- Verification Method: Inspection | Demonstration
- More Information: N/A

## 3.2 Display Server Accomodations

- ID: REQ-FUNC-002
- Title: Display Server Accomodations
- Statement: The system shall accomodate both Wayland and Xorg out of the box.
- Rationale: The Wayland server is the default, but some applications still use Xorg to function.
- Acceptance Criteria: All servers should be inspected and tested for issues that impede use.
- Verification Method: Inspection | Demonstration
- More Information: Most required programs are included from the CT version (baseline)


Requirement ID schema and traceability:
- ID format: REQ-[AREA]-[NNN]-[VER] (optional -[VER] if versioned), where AREA ∈ {FUNC, INT, PERF, SEC, REL, AVAIL, OBS, COMP, INST, BUILD, DIST, MAINT, REUSE, PORT, COST, DEAD, POC, CM, ML}.
- Uniqueness: IDs must be unique and immutable; changes increment -[VER] and are recorded in Revision History.
- Traceability: Each test artifact may reference the requirement ID.

💡 Tips:
- Make each requirement testable and unambiguous, using standard metrics and avoiding vague terms (e.g., “user-friendly,” “fast”).

### 3.1 External Interfaces
💬 _Specifies all external inputs and outputs, covering both required and provided interfaces._

➥ Provide interface definitions sufficient for implementation and test.

💡 Tips:
- Use interface control documents or schemas where appropriate and reference them here.

#### 3.1.1 User Interfaces
💬 _Describes how users interact with the system at a logical level._

➥ Define UI elements, flows, and standards to be followed (style guides, accessibility guidelines). Include layout constraints, common controls (e.g., help, search), keyboard shortcuts, error/empty-state behavior, and localization. Keep visual designs in a separate UI specification and reference them.

💡 Tips:
- Reference accessibility standards (e.g., WCAG) and platform-specific guidelines.
- Consider organizing into subcategories for clarity: Usability/Accessibility (inputs/outputs and dialogs to fit user abstractions, abilities, and expectations), and Convenience.

#### 3.1.2 Hardware Interfaces
💬 _Details interactions with physical devices and platforms._

➥ Specify (un)supported device types, data/control signals, electrical or mechanical characteristics if relevant, and communication protocols. Include timing, throughput, and reliability expectations.

💡 Tips:
- Reference applicable hardware specs and certification requirements.

#### 3.1.3 Software Interfaces
💬 _Defines integrations with other software components and services._

➥ List connected systems (name and version), required or provided services/APIs, data items/messages exchanged, communication styles/protocols, and limit/error/timeout semantics. Identify shared data and ownership.

💡 Tips:
- Capture versioning and backward compatibility policies.
- Define authentication/authorization expectations for each integration.

### 3.2 Functional
💬 _Specifies the externally observable behaviors and functions the software shall provide._

➥ Organize functional requirements by feature, use case, or service. For each, describe triggers/inputs, processing/logic (at a black-box level), outputs, and error conditions. For AI behaviors, define determinism bounds (e.g., temperature), refusal criteria, safety rules, and human review points.

💡 Tips:
- Include edge cases and negative scenarios for completeness.
- For AI features, include fallback behaviors and thresholds for abstention.

### 3.3 Quality of Service
💬 _Quality attributes that constrain or qualify functional behavior._

➥ Use specific metrics, ranges, and conditions.

💡 Tips:
- When a quality applies only to a subset of functions, reference the related requirement IDs.
- Provide rationale when targets cut across functions to aid trade-off decisions.

#### 3.3.1 Performance
💬 _Response time, throughput, and resource usage expectations._

➥ Specify timing relationships, peak/steady-state loads, and performance targets under expected conditions. Include measurement methods, environments, and acceptance thresholds. Note any real-time constraints.

💡 Tips:
- Include scalability targets and capacity planning assumptions.
- Consider organizing into subcategories for clarity: Time (latency, throughput, etc.) and Space (memory, storage, bandwidth, etc.).

#### 3.3.2 Security
💬 _Defines the protection of data, identities, and operations._

➥ Define authentication, authorization, data protection (in transit/at rest), auditing, and privacy requirements. Address abuse/misuse and external attacks (e.g., injection, data exfiltration, or service compromise), and include secure defaults and incident response requirements.

💡 Tips:
- Distinguish mandatory controls vs. recommended practices.
- Consider organizing into subcategories for clarity: Safety (harmful external outcomes), Confidentiality (disclose data to unauthorized parties), Privacy (private data disclosed without consent), Integrity (data modified without authorization), and Availability (authorized data or resources made available when requested).

📝 Note:
Place generic security controls here (3.3.2), and cross-reference from supported controls as necessary:
- Use 3.1 External Interfaces for interface-level validation and secure protocols.
- Use 3.4 Compliance for regulatory/contractual obligations and audit evidence.
- Use 3.6 AI/ML for model-specific runtime protections and data governance.

#### 3.3.3 Reliability
💬 _Ability to consistently perform as specified._

➥ Specify reliability metrics and techniques (e.g., MTBF, error budgets, retry/backoff, idempotency, redundancy). Define conditions under which reliability is assessed and any failover behaviors. Define graceful degradation (e.g., fallback components, cached results, AI/ML deterministic heuristics), timeout/abstain policies, and rollback to previous versions.

#### 3.3.4 Availability
💬 _System uptime and readiness to deliver service._

➥ Define availability targets, maintenance windows, and mechanisms like checkpointing, recovery, and restart. Include geographical/zone redundancy if applicable.

💡 Tips:
- Express availability in terms meaningful to users (e.g., downtime per month) and tie to SLAs/SLOs.
- Capture scale-out/in behavior affecting availability (e.g., max failover time, quorum constraints).

#### 3.3.5 Observability
💬 _Ability to understand system state and behavior in production through telemetry._

➥ Define requirements for logs, metrics, traces, and profiling: events/fields, cardinality limits, sampling, retention, and privacy/PII handling in telemetry. Specify standard labels (e.g., service, version, tenant), correlation/trace IDs propagation, and redaction policies. State SLO-aligned alert rules, dashboards, and ownership.

💡 Tips:
- Avoid maintenance-process details (keep runbooks and on-call policies in 3.5.4 Maintainability).

### 3.4 Compliance
💬 _Requirements derived to satisfy external standards, regulations, or contracts._

➥ Specify mandated formats, naming conventions, accounting procedures, provider/user rights and agreements, licensing agreements, audit tracing, records retention, and reporting. For each compliance item, reference 2.3 Product Constraints if applicable, or cite the authoritative source directly.

### 3.5 Design and Implementation
💬 _Constraints or mandates affecting how the solution is designed, deployed, and maintained._

#### 3.5.1 Installation
💬 _Ensures the software runs smoothly in its target environments._

➥ Define (un)supported platforms/environments, prerequisites, installation methods, environment configuration (e.g., env vars, secrets), and rollback/uninstall procedures.

💡 Tips:
- Detail automation expectations (e.g., IaC, installer scripts, container images).
- Keep scaling mechanics (topology, multi-region) in 3.5.3 Distribution; keep scaling targets in 3.3 QoS.

#### 3.5.2 Build and Delivery
💬 _Defines the controls for building, packaging, and delivering software artifacts to ensure integrity, traceability, and reproducibility._

➥ Define how source code is transformed into deployable artifacts and moved through environments. Describe expectations for build reproducibility, dependency management, licensing, configuration management, artifact verification, and release promotion.

💡 Tips:
- Cross-reference 3.5.1 Installation and 3.5.10 Change Management for environment setup, versioning, and release traceability.
- Avoid operational topology details (those belong in 3.5.3 Distribution).

#### 3.5.3 Distribution
💬 _Addresses geographically or organizationally distributed deployments, data, and devices._

➥ Specify deployment topologies, component and data distribution/replication approaches and scale-out runbooks, and constraints imposed by organizational or network structure.

#### 3.5.4 Maintainability
💬 _Attributes that make the software easier to modify, fix, and evolve._

➥ Define expectations for modularity, code complexity, interfaces, coding standards, developer oriented observability, documentation, software delivery performance, and technical debt management.

#### 3.5.5 Reusability
💬 _Encourages leveraging components across products or contexts when appropriate._

➥ Identify components intended for reuse and any constraints on their dependencies or technology choices. Specify modularization, API stability, packaging, and documentation to enable reuse.

#### 3.5.6 Portability
💬 _Ability to run on multiple platforms or environments with minimal changes._

➥ Specify (un)supported operating systems, hardware architectures, cloud providers, or container runtimes. Define abstraction layers, configuration policies, and externalization of environment-specific settings.

#### 3.5.7 Cost
💬 _Financial considerations or cost targets._

➥ State budgetary limits, cost-per-transaction targets, licensing constraints, or cloud spend envelopes that influence design decisions.

💡 Tips:
- Keep costs high-level unless contractually defined.
- Link to a cost model or TCO assumptions where available.
- Note variable vs. fixed cost expectations impacting scaling strategies.

#### 3.5.8 Deadline
💬 _Schedule expectations that affect scope and prioritization._

➥ Specify key milestones, delivery dates, or phases/increments. Indicate dependencies between milestones and required readiness criteria.

💡 Tips:
- Use deadlines to guide apportioning of requirements (Section 2.6).

#### 3.5.9 Proof of Concept
💬 _Validates feasibility and de-risks critical assumptions before full-scale delivery._

➥ Define the objectives, scope, success criteria, and timebox for any POCs. Describe what will be validated (technical, usability, performance) and how results will influence requirements or design.

💡 Tips:
- Keep POCs narrowly focused and measurable. Focus on validation goals, not implementation details.

#### 3.5.10 Change Management
💬 _Controls how changes are introduced and communicated._

➥ Define change categories (breaking, additive, bugfix), approval workflow, and required artifacts (changelogs, evaluation summaries, migration guides, release notes). Specify backward/forward compatibility guarantees, client communication plans, deprecation timelines, and rollout/rollback procedures.

## 4. Verification
💬 _Describes how each requirement will be verified to provide objective evidence of compliance._

➥ Outline verification methods (test, canary metrics, analysis, inspection, demonstration) and test evidence preferably in a matrix paralleling Section 3. Consider adding environment details, tools, and test data requirements.

| Requirement ID | Verification Method | Test/Artifact Link | Status | Evidence           |
|----------------|---------------------|--------------------|--------|--------------------|
| REQ-FUNC-001   | test                | tests/UC01.md      | Passed | reports/tuc01.html |
| REQ-SEC-003    | analysis            | threat-model.md    | WIP    |                    |

💡 Tips:
- Include both positive and negative tests and include non-functional verification (performance, security, reliability).
- Verification artifacts may be versioned and linked to CI/CD.
- For AI, reference Model Cards and track eval datasets’ versions and ensure reproducibility of results.

## 5. Appendixes
💬 _Optional supporting material that aids understanding without being normative._

➥ Include glossaries, data dictionaries, models/diagrams, sample datasets, or change-impact analyses that support the main sections. Reference rather than duplicate content when possible.

💡 Tips:
- Keep appendixes organized and referenced from the main text.

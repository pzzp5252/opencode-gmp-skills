# Security model — opencode-gmp-skills

This is the threat model used by Devin security scans. It is shared across pzzp5252's five repositories (claude-code-sourcemap, dji-remote-c3, hvac-validation-docs, opencode-gmp-skills, web-slide-fps), which are unrelated systems scanned separately. This file covers **opencode-gmp-skills**. Facts marked **(owner)** come from the repository owner; the rest is read from the code. No infrastructure repository exists: these are local tools, firmware and research code, nothing hosted **(owner)**.

## Components

| Component | Code | Trust boundary |
|---|---|---|
| GMP-Skills | `capa-officer/SKILL.md`, `validation-specialist/SKILL.md` | Text loaded into an AI agent's context |

## System overview

Two Markdown agent skills (CAPA officer, validation specialist) for Chinese GMP work. No executable code.

## What matters

- Instructions that could lead an agent to fabricate or misstate GMP records, results or signatures affect the owner's critical asset (GMP record/data integrity) (inferred).
- Kept in scans despite having little code **(owner)**.

## Owner priorities across all repositories

- Integrity of GMP validation records and reports (data integrity, ALCOA+) **(owner, critical)**.
- Camera control and take/journal integrity in the field **(owner, critical)**.
- Developer/QA workstations that run these tools **(owner)**.

## Finding tags

- `Component` (table above), `CVE` for known dependency vulnerabilities, `GMP-relevance` = yes when the finding could affect GMP record/report or data integrity (ALCOA+), otherwise no **(owner)**.

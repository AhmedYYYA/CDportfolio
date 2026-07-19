# Verification report — Falcon Aviation Command v2.0

**Test date:** 2026-07-18  
**Artifact:** `index.html`  
**Artifact size:** 454,067 bytes  
**SHA-256:** `88b18b181c628ecba60778431ba7c7d9d573fb7d6b4178f08dd611364dcc5a0c`  
**Dataset seed/hash:** `FAC-DEMO-2026` / `148da55f`

## Release result

**PASS — no release-blocking failure found in the tested static-demo scope.**

| Verification layer | Result | Evidence |
|---|---:|---|
| JavaScript evaluation and deterministic generation | PASS | One embedded script evaluated; 48 assets and all domain datasets generated; repeatable dataset hash `148da55f` |
| In-app calculation assurance | 16 / 16 PASS | Ledger identity, pool conservation, non-negative guards, CPFH/EVM/PV/EUAC/ROP guards, i18n, platform schema, downtime integrity, task applicability, PO reconciliation, SLA timing, route rendering, CSV neutralization |
| Major-page bilingual rendering | PASS | 32 pages in English and Arabic; no exceptions, missing markers, `undefined`, or `[object Object]` leaks |
| Parameterized bilingual rendering | 210 / 210 PASS | Five platform pages, 48 aircraft pages, 20 capability pages, 17 scenario runs, and 15 reports in both languages |
| DOM interaction workflows | 17 / 17 PASS | Pre-login command blocking, role selection, disclaimer, route/domain scene, executive brief, Decision Studio, command shortcut/filter, RTL switch, spares/PO pipeline, persistence, Auditor write block, OEM scope, malformed-route recovery |
| Representative automated accessibility scan | PASS | No violations reported by the supported WCAG 2.2 A/AA rules on login, dashboard, English spares, and Arabic spares; colour-contrast automation was excluded in the DOM-only environment |
| Documentation consistency | PASS | Acceptance JSON parses; 60 evidence items reconcile to 53 implemented, 4 bounded limitations, and 3 production extensions |

## Deterministic headline outputs

| Measure | Value |
|---|---:|
| Fleet availability (Ao) | 83.2% |
| NH90 availability (Ao) | 69.0% |
| Supply fill rate | 89.2% |
| NH90-applicable fill rate | 84.2% |
| Portfolio health | 80 / 100 |
| Direct / burdened CPFH | 13,955 / 24,398 AED/FH |
| Future decision-model fleet PV | 5,797M AED |
| Deterministic P50 / P80 | 5,935M / 6,181M AED |

## Dataset integrity observations

- 239 downtime events carry explicit start/end days; no aircraft-month interval overlaps or exceeds its calendar month.
- Work-order tasks respect the platform applicability matrix.
- All 6,000 ledger rows satisfy `opening + receipts − issues + adjustment = closing`.
- Every receipt-bearing ledger row links to a received purchase order and receipt identifier.
- The 141 open purchase orders total 995 units, exactly matching aggregate due-in stock.
- FSR response and resolution flags equal the recorded duration-versus-agreement comparison.
- Auditor write attempts do not mutate session risks; OEM command data contains eight releasable cases and no internal aircraft records.

## Accessibility and visual acceptance boundary

The DOM audit verifies structure, names, states, landmarks, captions, and supported WCAG rules. Final production acceptance should still include visual review on the target browser/device matrix, colour-contrast measurement of every state, 200%/400% zoom, screen-reader exercises, keyboard-only testing, print/PDF review, and user testing with Arabic readers.

## Security and operational boundary

This release intentionally demonstrates authorization and governance in the browser. It is not a security boundary. Production use requires server-side identity and authorization, append-only audit, approved data classification, controlled integrations, monitoring, backup, and independent security assurance.

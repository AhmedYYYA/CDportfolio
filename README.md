# Falcon Aviation Command v2.0

**Demonstration environment — synthetic data — not operational**  
**بيئة عرض توضيحي — بيانات اصطناعية — غير تشغيلية**

Falcon Aviation Command is a self-contained, bilingual capability-portfolio and aviation-lifecycle decision cockpit for a fictional organisation. The entire experience—interface, deterministic data generator, calculations, role model, charts, and documentation—ships in one `index.html` file with no external runtime dependency.

## Start

Open `index.html` in a current browser. Choose one of the 15 demonstration roles, acknowledge the data boundary, and use the control tower locally. No server or build step is required.

For GitHub Pages, upload `index.html` to the repository root, then enable **Settings → Pages → Deploy from a branch → main / root**.

## What changed in v2.0

- A compact, elegant glass cockpit with a dark command rail, selective frosted surfaces, solid high-density tables, refined motion, and print-safe output.
- Six contextual visual environments—Command, Capability, Fleet, Modernization, Cost, and Governance—with route-specific abstract artwork and background treatment.
- An integrated executive brief connecting portfolio health, fleet posture, decision lineage, and three leadership priorities.
- A live Decision Studio with governed flying-hour, supply-lead-time, and fuel-price drivers; outputs are bounded and explicitly labelled as illustrative.
- A keyboard command palette (`Ctrl/Command + K` or `/`) searching authorized routes, capabilities, programmes, aircraft, parts, risks, and support cases.
- Compact/expanded navigation, mobile layouts, full English/Arabic RTL switching, keyboard focus management, reduced-motion support, forced-colour support, and accessible table semantics.
- Corrected synthetic-data mechanics: possessed-hour availability, non-overlapping downtime, calendar-accurate months, time-window-aligned reliability, active-repair MTTR, platform-applicable maintenance tasks, backorder carry-forward, and timestamp-derived service-level attainment.
- Purchase-order and receipt lineage for stock receipts, including an interactive inbound pipeline that reconciles exactly to the due-in balance.
- Persistent role, preference, scenario, approval, risk, and audit state with a complete reset path.
- Stronger role behavior: Auditor mutations are blocked; OEM search, pages, and service-level widgets remain releasable-record scoped.

## Demonstration dataset

| Domain | Synthetic content |
|---|---|
| Fleet | 48 aircraft across five helicopter families and three fictional sites |
| History | 36 months through 2026-06-30; 180 usage rows and 153 possessed-availability rows |
| Maintenance | 340 work orders, 185 fault observations, 239 non-overlapping downtime episodes |
| Supply | 500 parts, 6,000 monthly ledger rows, 2,481 purchase orders, 120 repairable pools, 52 repair orders |
| Commercial support | 12 agreements and 30 field-service representative cases |
| Portfolio | 20 capabilities, 10 programmes, 8 upgrades, 25 obsolescence items, 20 risks, 20 actions, 11 decisions, 10 assumptions |
| Economics | 960 cost rows and a 2026–2055 decision-support lifecycle model with PV, EUAC, deterministic P50/P80, and tornado sensitivity |
| Decision support | 17 governed scenarios plus the three-driver live Decision Studio |

Public platform facts are kept structurally and visually separate from synthetic operational records. Each public assertion carries its source, applicability note, confidence state, and retrieval date. Public specifications are never used to infer synthetic fuel burn, maintenance, cost, reliability, availability, or mission performance.

## Determinism and evidence

| Field | Value |
|---|---|
| Release | `2.0.0` |
| Seed | `FAC-DEMO-2026` |
| PRNG | xfnv1a-labelled mulberry32 streams |
| Data as-of | `2026-06-30` |
| Horizon | 2026–2055 |
| Dataset hash | `148da55f` |
| Translation parity | 1,310 English keys = 1,310 Arabic keys |
| In-app assurance | 16 / 16 PASS |

Verification on this exact release includes:

- 32 major pages rendered in English and Arabic with no exceptions, missing markers, `undefined`, or object-string leaks.
- 210 parameterized platform, aircraft, capability, scenario, and report views rendered cleanly in both languages.
- 17 / 17 DOM interaction workflows passed: login, pre-login command blocking, disclaimer, routing, contextual scenes, decision controls, command search, RTL, inbound pipeline, persistence, Auditor write blocking, OEM scoping, and malformed-route recovery.
- Automated WCAG 2.2 A/AA checks on login, dashboard, English spares, and Arabic spares returned no violations in the test environment; colour contrast is governed by the design tokens and should still be confirmed in the target browser/device matrix.
- Ledger identity, repairable conservation, no-negative guards, finance identities, platform schema, downtime interval integrity, maintenance applicability, purchase-order reconciliation, SLA timing, bilingual parity, route rendering, and CSV formula neutralization all pass live in **Governance → Calculation assurance**.

Headline synthetic outputs are fleet Ao 83.2%, NH90 Ao 69.0%, fill rate 89.2%, portfolio health 80/100, four critical open risks, and two decision-pending obsolescence shortages inside 18 months. These are deterministic demonstration outputs, not operational claims.

## Interaction guide

- Use the top search control or `Ctrl/Command + K` to reach records quickly.
- Use the navigation toggle to switch between compact and expanded views.
- On the Commander dashboard, adjust the Decision Studio ranges and reset them at any time.
- Select the reverse-face icon on KPI cards to inspect formula, inputs, origin, and time window.
- Sort, page, and export data tables. CSV exports include the synthetic-data boundary, filters, seed, dataset hash, origin legend, and timestamp; spreadsheet formulas are neutralized.
- Switch to Arabic at any time; the complete interface mirrors to RTL while identifiers and numerals remain readable.

## Scope and limitations

- All roles, approvals, mutations, and audit events run client-side for demonstration. They illustrate a governance model and are not security controls.
- Operational records are entirely fictional and must never be combined with real sensitive data in this static build.
- Lifecycle totals cover synthetic operating/support, modernization, obsolescence, retirement, and residual-value decisions. Historical acquisition is treated as sunk cost and is not reconstructed.
- SVG visualizations are dependency-free. Important values also appear as cards or tables, but this release does not claim a data-table toggle for every chart.
- Public-fact evidence is a dated snapshot; items labelled `REQUIRES_VALIDATION` must be rechecked before reuse.
- A production pilot requires authenticated server-side RBAC, append-only audit, database constraints, approved data classification, and governed read-only integrations.

## Files

- `index.html` — complete deployable website and source.
- `README.md` — start, scope, architecture, and verification summary.
- `IMPLEMENTATION_STATUS.md` — requirement-by-requirement delivery status.
- `acceptance-matrix.json` — machine-readable acceptance evidence.
- `VERIFICATION_REPORT.md` — release test record.

## ملخص عربي

الإصدار 2.0 منصة قيادة تفاعلية حديثة في ملف واحد، تعمل دون خادم أو تبعيات خارجية. تتضمن ست بيئات بصرية بحسب مجال العمل، وموجزاً قيادياً، واستوديو قرار تفاعلياً، وبحثاً سريعاً، وواجهة عربية كاملة من اليمين إلى اليسار.

جميع السجلات التشغيلية اصطناعية وحتمية التوليد من البذرة `FAC-DEMO-2026`، وبصمة مجموعة البيانات هي `148da55f`. أما الحقائق العلنية عن المنصات فتبقى منفصلة مع مصادرها وحدود انطباقها. اجتاز الإصدار 16 من 16 فحص ضمان داخل التطبيق، إضافة إلى اختبارات التفاعل والعرض الثنائي اللغة الموضحة أعلاه.

هذه النسخة عرض توضيحي يعمل داخل المتصفح؛ ولا تمثل نظام صلاحيات أو سجلاً تدقيقياً آمناً للإنتاج.

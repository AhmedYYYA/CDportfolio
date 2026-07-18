# FALCON AVIATION COMMAND — Capability Portfolio & Lifecycle Control Tower
# قيادة طيران الصقر — منصة إدارة محافظ القدرات ودورة الحياة

**DEMONSTRATION ENVIRONMENT — SYNTHETIC DATA — NOT OPERATIONAL**
**بيئة عرض توضيحي — بيانات اصطناعية — غير تشغيلية**

A single-file, fully interactive, bilingual (English / العربية RTL) static demonstration of a
helicopter capability-portfolio and lifecycle control tower for a fictional organisation.
Zero dependencies, zero network calls, zero build step — one `index.html`.

**v1.1** — refined visual design system (hero login, grouped role selection, motion, elevated cards/tables/navigation) and a full bilingual QA pass (disclaimer text added in both languages, gate codes normalised to G0–G11, aviation terminology corrections in Arabic).

---

## 1) Quick start

Open `index.html` in any modern browser. That's it.

- Choose one of **15 demonstration roles** (Commander, Capability Director, Fleet Manager,
  Supply, Finance, OEM external, Auditor, …). Navigation, widgets, and permissions change per role.
- Toggle **العربية / English** at any time — the full interface mirrors to RTL.
- Everything runs locally in the browser; state (role, saved scenario runs, acknowledgements)
  is kept in `localStorage` and cleared by **Administration → Reset demonstration**.

## 2) Deploying to GitHub Pages from an iPhone

1. In the GitHub app or Safari, open your repository → **Add file → Upload files**.
2. Upload `index.html` to the repository root (or a `/docs` folder).
3. Repo **Settings → Pages** → Source: *Deploy from a branch* → select `main` and `/ (root)`
   (or `/docs`) → **Save**.
4. Wait ~1 minute; the site is live at `https://<user>.github.io/<repo>/`.
5. Updates: upload a new `index.html` over the old one — Pages redeploys automatically.

No build pipeline, no Actions, no secrets. The file is self-contained.

## 3) What is inside (verified by the built-in test suite)

| Area | Content |
|---|---|
| Fleet | 48 synthetic aircraft: 8× CH-47F, 16× UH-60M (two cohorts), 8× AH-64E, 8× NH90 NFH, 8× H145M, across 3 fictional sites |
| History | 36 months of usage, downtime, availability (Jul 2023 – Jun 2026), as-of **2026-06-30** |
| Records | 340 work orders · 185 fault observations · 240 downtime episodes · 500 parts · **6,000 ledger rows** · 120 repairable pools · 52 repair orders · 12 agreements · 30 FSR cases · 8 upgrades (EVM) · 25 obsolescence items · RAID 20/20/11/10 |
| Economics | FY2026 cost stack (budget / *Synthetic Actual* / forecast — never summed), fuel price series, CPFH inclusion matrix v1.0, 30-year LCC to 2055 with PV, EUAC, 2,000-run deterministic Monte-Carlo (P50/P80) and tornado |
| Governance | Stages 0–9, gates G0–G11, maker–checker approval with **self-approval blocked**, immutable scenario-run log, audit trail incl. denied access, 15 print frames, data-quality rules, formula dictionary (28 governed formulas), calculation-assurance page running live checks in-browser |
| Scenarios | 17 governed what-ifs with declared coefficient set v1.0 and explicit “Effect not modelled” lists |

### Public facts vs synthetic data
Platform pages keep three visually separated sections: **Public reference facts (verbatim,
with source link + retrieval date)** → **Synthetic fleet & operations** → **Derived indicators**.
Sources SRC-01…SRC-10 are listed on the Source Register page; three are marked
`REQUIRES_VALIDATION` (PZL S-70 page and two NHIndustries URLs not directly re-confirmed on
2026-07-16). Fuel-burn rates are **synthetic planning assumptions (AS-01)** — never derived
from public specifications.

## 4) Determinism — seed manifest

| Field | Value |
|---|---|
| Seed | `FAC-DEMO-2026` |
| PRNG | mulberry32 + xfnv1a label streams |
| As-of date | 2026-06-30 · base year 2026 · horizon 2026–2055 |
| FX (display) | 3.6725 AED/USD · inflation 2.2% · real discount 3.0% (Fisher → 5.266% nominal) |
| **Dataset hash** | **`f68a97db`** (FNV-1a over core dataset — identical on every load, any device) |

## 5) Test results (executed on this exact file)

`34 / 34 PASS` — including: identical hash across independent loads; ledger identity
`open + receipts − issues ± adj = close` on all 6,000 rows; repairable 7-state conservation
on all 120 pools; no negatives anywhere; cost roll-ups equal element and platform sums;
actual/forecast month windows disjoint; CPFH → N/A at zero FH and burdened > direct
(13,955 / 24,398 AED/FH); PV = plain sum at r = 0, PV < undiscounted, EUAC = PV·A(r,N) for all
platforms; ROP/SS/EOQ match hand calculations; EVM guards (UPG-01 excluded at AC = 0, CPI < 1
case shows EAC1 > BAC); self-approval blocked / cross-role approval accepted; OEM role
restricted to its three routes and sees only releasable FSR cases; 1,208 = 1,208 bilingual key
parity; 230 route renders across EN+AR × 4 roles with zero errors, zero missing-translation
markers, zero stray `undefined`; CSV export neutralizes `= + − @` and stamps a governance
header (banner, filters, seed, hash, origin legend, timestamp).

Headline demo figures: fleet Ao **82.1%** (NH90 **67.9%** — designed recovery story, with a
March-2025 outlier at 0.55 for drill-down), fill **91.9%** (NH90-applicable parts 86.5%),
portfolio health **81/100** with 4 critical risks and exactly 2 decision-pending shortages
inside 18 months, fleet 30-year PV **5,797M AED** (P50 5,935M · P80 6,181M).

## 6) Known limitations (by design of a static demo)

- **All enforcement is client-side.** Roles, approvals, and the audit log demonstrate the
  governance *model*; they are not security controls. A real deployment implements RBAC,
  maker–checker, and append-only audit **server-side**.
- State lives in the browser; clearing site data resets the demo.
- Charts are dependency-free SVG; print frames rely on the browser's print dialog.
- Public-fact snapshot is frozen at 2026-07-16; three sources remain flagged for validation.
- Scenario coefficients, health-index weights, and the CPFH matrix are **governed demo
  assumptions** (v1.0), surfaced in-app precisely so they can be challenged.

## 7) Phase 2 — path to an authorized pilot

The natural next step is a full-stack build (e.g. via Claude Code in a connected environment):
Next.js/React front end, PostgreSQL with the same schema semantics (ledger identity and pool
conservation as database constraints), server-side RBAC + maker–checker + append-only audit,
SSO, and read-only connectors to ERP/MRO/PLM/logistics — reusing this demo's formula registry,
i18n dictionary, and scenario coefficient governance as the specification.

---

## بالعربية — ملخص سريع

هذا ملف واحد `index.html` يعمل في أي متصفح حديث دون أي تبعيات أو اتصال بالشبكة.
اختر أحد **15 دوراً** للعرض؛ وبدّل اللغة بين العربية والإنجليزية في أي لحظة (واجهة يمين-إلى-يسار كاملة).

**النشر على GitHub Pages من الآيفون:** ارفع الملف إلى جذر المستودع، ثم من
Settings → Pages اختر النشر من الفرع `main` والمجلد الجذري، وستعمل الصفحة خلال دقيقة تقريباً.

جميع البيانات التشغيلية **اصطناعية وحتمية التوليد** (البذرة `FAC-DEMO-2026`، البصمة `f68a97db`)،
وتُعزل الحقائق المرجعية العلنية في قسم مستقل بنصها الحرفي مع روابط مصادرها وتواريخ الاسترجاع،
وتُعلَّم معدلات استهلاك الوقود بوصفها افتراضات تخطيطية اصطناعية (AS-01).
اجتاز الملف **34 من 34** فحصاً آلياً، من ضمنها مطابقة دفتر المخزون على 6,000 صف، وحفظ الحالات
السبع للقطع القابلة للإصلاح، وحجب الاعتماد الذاتي في البوابات، وتكافؤ القاموس الثنائي
(1,208 = 1,208 مفتاحاً). صفحة «ضمان الحسابات» داخل التطبيق تعيد تنفيذ هذه الفحوص حياً في متصفحك.

**قيد جوهري:** كل الضوابط في هذا العرض تعمل داخل المتصفح لغرض التوضيح فقط؛ والنشر الفعلي
يستلزم تطبيق الصلاحيات والاعتماد المزدوج وسجل التدقيق على الخادم (المرحلة الثانية).

# Cable Thermal Studio — original build, full feature parity and numerical verification

**Assessment date: 26 October 2026.** All steps concern the user-supplied original v3.6.2 application plus protected public browser release. Previous working public calculations and all 93 audited source sheets have been preserved.

## Gate 1 — Original React/Vinext production compilation

**Result: NOT VERIFIED; actual build execution failed.** Recovered full original application, pinned `pnpm-lock.yaml` and original Node scripts. Restored authoritative 93-sheet workbook at the path required by its source verifier (SHA-256 `d38a19c7e28a4fe79d399d2ff498653b5febc5878d8ddafc155f888cc9855ba5`). `node v22.16.0` satisfies package Node >=22.13.0. Running the actual `npm run build` returned `ERR_MODULE_NOT_FOUND: node_modules/vinext/dist/cli.js`. Neither pinned React nor Vinext is installed; `registry.npmjs.org` DNS resolution fails. The original SSR app has not been compiled or deployed. Source syntax QA is not a substitute for this build.

Source recovery checkpoint **10/10 PASS**, **119/119 Node test assertions PASS**; this checkpoint intentionally labels source PASS but release BLOCKED. Evidence: `production_build_log.txt`, `original_source_checkpoint.json`.

## Gate 2 — Original versus public feature parity

**Result: IMPROVED, NOT FULLY VERIFIED.** Evaluated 29 original feature contracts against original source and public HTML plus original-source modules. The public archive detects UI for 23/29 source contracts; those are **presence checks**, not proof of behavior identical to the original React page. Outstanding comparisons include full 20-circuit and geometry editing, configurable 2-D mesh/domain independence, scenario editor, original study schema roundtrip and original React SSR routes. Detailed per-feature evidence: `feature_parity_audit.md` and `.json`.

### Added public functionality

A new **Cable ranking & code comparison** page is live at:

https://headless-vmwfmgemqxl-classroomsolar-140e.wix-site-host.com/compare.html

It uses the **unchanged** recovered `lib/candidate-ranking.mjs` and `lib/rating-comparison.mjs` engines deployed as browser modules; handles all 13,223 original CABLES source records plus device-local custom records; requires provenance for sharing and published code factors; displays all candidate set trials; offers CSV export; supports original-study JSON import and feet/inches/metric controls. Test scenarios include a synthetic positive ranking, four forward trials, a synthetic condition-matched three-way calculation, missing-reference fail-closed behavior, 4 browser widths (320, 390, 768, 1440 px) and two-way unit conversion. Synthetic data are labelled as non-manufacturer fixtures.

The **existing 151 public release files were all retained**. **149 remain byte-for-byte unchanged**. Only `index.html` and `workspace.html` received navigation links, and three new files (`compare.html`, `compare.css`, `compare.js`) were added. All existing numerical libraries, application JS and 94 data assets (93 worksheets + manifest) are unchanged. SHA-256 hashes and archive CRC were checked. Public deployment contains **154 files**. Public home and comparison page both responded to unauthenticated independent fetch.

## Gate 3 — Independent engineering calculation verification

**Result: 540/540 new independent synthetic cases; 3,600/3,600 component comparisons pass. Full project-specific method approval NOT established.** The independent Python oracle does not import numerical source modules. It rederives three mathematical contracts and compares the original source and published unchanged JS libraries:

| Calculation | Independent synthetic samples | Scope |
|---|---:|---|
| IEC 60287 current rating and temperature supplied-loss equation | 300 | 1/2/3 cores with explicit T1–T4, Rac, dielectric, sheath and armour factors |
| Concentric single-core insulation/jacket thermal resistance | 120 | Independent logarithmic cylindrical resistance equations |
| Paired sensor temperature validation | 120 | MAE, RMSE and maximum absolute error |

All 3,600 scalar checks passed; the original and public source results match for each fixture. Additional targeted Node tests **23/23 PASS**, covering IEC input guards, historical Wolfram scalar fixtures, step-refined four-node transient matrix checks, manufactured heterogeneous 2-D field and candidate/code comparison workflows. A fresh Wolfram calculation reproduced three example IEC current ratings (629.68914765, 458.66676783, 377.90564128 A) and load temperatures (66.0825, 102.145, 138.2075°C).

The calculations above are **not** cable product certification or proof of complete IEC 60287 / IEC 60853 implementation for every topology. No independent manufacturer laboratory data, detailed field-test dataset, complete project-specific losses/soil/duct materials or qualified engineering signoff were supplied. Published references: [IEC 60287-1-1:2023](https://webstore.iec.ch/en/publication/68118), [IEC 60287-2-1:2023](https://webstore.iec.ch/en/publication/68134). These standards explicitly depend on correctly chosen construction and environment parameters.

## Integrity conclusion and conditions for claiming 100%

- **Public browser calculator:** live, extended, existing engine/catalogue protected.
- **Original React/Vinext production application:** not compiled; cannot claim production-build verification or true browser SSR parity.
- **Numerical checks listed above:** PASS; no evidence for blanket independent physical-method approval or site-specific engineering certification.

Do not label the original app or all advanced thermal studies “100% verified” until a real pinned-dependency build, compiled React browser acceptance and independent applicable physical benchmarks/qualified signoff exist. No unverified flag has been changed to PASS in this assessment.

# Cable_Thermal_Calculator_prompt
## Trench, Underground Cable & Duct Bank Thermal Calculator

| Item | Detail |
|---|---|
| Calculator | **Cable_Thermal_Calculator** |
| Status | Existing calculator — continue and complete on the website |
| Website page | `/underground-cables` (cable arrangement, ampacity, soil and duct bank thermal, cyclic/emergency, trench documentation) |
| Master Prompt V5.0 scope | Group 8 — Trench, Underground Cable and Duct Bank Electrical Design (R165–R185) + shared engine IDs R272, R273 |
| Project types | P1 utility fixed-tilt, P2 utility single-axis tracker, P3 commercial carport, P4 commercial/industrial rooftop, P5 residential rooftop — applicability recorded per requirement (REQUIRED / CONDITIONAL / NOT APPLICABLE / UNSUPPORTED, Section 19) |
| Revision | Final — 14 November 2026 |

## 0. About this file

- This is the **only** project document for this calculator. It replaces every earlier README, prompt, handoff and requirement document; everything still needed from them is written here.
- Governing specification: **Master Prompt V5.0** (Integrated Electrical PV Design Engineering Platform, 9 November 2026). Give the AI both this file and the Master Prompt at the start of every session. If the two ever disagree, the Master Prompt wins.
- The calculator is part of **one integrated public website** (Master Prompt Sections 2, 43, 80): its own route/page, shared project data, shared equipment database, shared reports.
- Reply to the owner in **Hinglish** (simple Hindi–English). Write code, reports and documents in English.
- The owner is an electrical / PV design engineer, not a software developer. The AI does the research, design, coding, testing, debugging and documentation itself (Master Prompt Sections 1–4).


## 1. What this calculator does

Underground cable configuration and spacing, trefoil and flat arrangements, ampacity using supplied soil thermal resistivity, installation and multi-circuit derating, direct-buried suitability, duct-bank configuration and thermal calculation, concrete-encased duct banks, underground conduit fill, short-circuit withstand, voltage drop, pulling (shared engine), MV shield and bonding checks, underground cable/duct-bank schedules and trench allocation (Group 8, R165–R185). It owns the shared underground / duct-bank thermal engine also used for MV cables (R272, R273). Soil thermal resistivity is always supplied data. Above-ground cable thermal needs its own verified method — never reuse the underground method above ground (Section 37).

**Scope boundary:** Never build, anywhere in this calculator: generator sources or sizing, HV / EHV equipment or studies (above the 35 kV class), substation engineering, field testing / measurement / commissioning, structural / civil / mechanical calculations, and any financial or cost calculation (equipment prices, CAPEX, OPEX, LCOE, tariffs). BESS is deferred (Master Prompt Section 18): do not build it now, but keep data models ready for it. Everything is built on the public website — no spreadsheets, no VBA, no desktop tools.


## 2. Requirements of this calculator


### 2.1 Functional requirements from Master Prompt V5.0

Every requirement below must end up implemented and verified, or marked NOT APPLICABLE / NOT SUPPORTED with a written reason. "Current state" is the starting point found in the earlier work; confirm it in Phase 0.


**Group 8 — Trench, Underground Cable and Duct Bank Electrical Design (R165–R185, 21 active)**

| ID | Requirement (Master Prompt V5.0, verbatim) | Current state |
|---|---|---|
| R165 | Underground cable configuration assessment. | Built earlier — verify |
| R166 | Underground cable spacing calculation. | Built earlier — verify |
| R167 | Trefoil cable arrangement assessment. | Built earlier — verify |
| R168 | Flat cable arrangement assessment. | Built earlier — verify |
| R169 | Underground cable ampacity calculation. | Built earlier — verify |
| R170 | Soil thermal-resistivity-based cable thermal assessment using supplied data. | Built earlier — verify |
| R171 | Underground ambient and installation-condition derating. | Built earlier — verify |
| R172 | Multiple-circuit thermal derating. | Built earlier — verify |
| R173 | Direct-buried cable suitability assessment. | Built earlier — verify |
| R174 | Duct-bank configuration design. | Partly built — complete |
| R175 | Duct-bank electrical thermal calculation. | Partly built — complete · shared engine: Duct-bank and underground thermal calculations |
| R176 | Concrete-encased duct-bank thermal assessment. | Partly built — complete · shared engine: Duct-bank and underground thermal calculations |
| R177 | Underground conduit-fill calculation. | Logic exists in another calculator — reuse one engine |
| R178 | Underground cable short-circuit withstand assessment. | Partly built — complete |
| R179 | Underground cable voltage-drop calculation. | Not built — build new |
| R180 | Underground cable-pulling tension calculation. | Logic exists in another calculator — reuse one engine · shared engine: Cable pulling tension, sidewall pressure and bend radius |
| R181 | Underground cable sidewall-pressure calculation. | Logic exists in another calculator — reuse one engine · shared engine: Cable pulling tension, sidewall pressure and bend radius |
| R182 | Underground cable bend-radius and pulling assessment. | Logic exists in another calculator — reuse one engine · shared engine: Cable pulling tension, sidewall pressure and bend radius |
| R183 | MV shield and bonding arrangement checks. | Built earlier — verify |
| R184 | Underground cable and duct-bank schedule. | Not built — build new |
| R185 | Trench cable allocation and electrical arrangement documentation. | Not built — build new |

**Shared engine built here and used by other calculators (Master Prompt Section 23)**

| ID | Requirement (verbatim) | Listed in the group of |
|---|---|---|
| R272 | MV trench cable thermal assessment. | MV_Electrical_Design_Calculator |
| R273 | MV duct-bank thermal assessment. | MV_Electrical_Design_Calculator |

### 2.2 Additional requirements from this calculator's earlier documents

These came from the earlier README / prompt / requirement documents and are kept because they match Master Prompt V5.0.

| # | Requirement | Matches V5.0 |
|---|---|---|
| D01 | Focus only on underground cable ampacity / cable thermal; no tray, fault, protection, grounding, voltage-drop or BOM calculators here | Group 8 boundary; Sections 43, 49 (integration through contracts) |
| D02 | Responsive UI, no text overflow; clear inputs, charts, cross-sections | Sections 73–75 |
| D03 | Manual cable construction or DB record; custom cables with import/export, provenance, duplicate protection | Section 44 (overrides, provenance) |
| D04 | Steady-state ampacity, conductor temperature, IEC 60287 loss paths (R20, skin/proximity, dielectric, sheath, armour, T1–T4) | R169–R171, R257 |
| D05 | Direct-buried single-core; trefoil/flat/vertical/custom; spacing, depth, multiple circuits, unequal loads | R165–R168, R172–R173 |
| D06 | AC 3PH/1PH and DC systems, parallel sets, current-sharing evidence | R165, R169 |
| D07 | Sheath bonding and circulating losses: single-point, both-ends, cross-bonding; armour paths | R183, R264–R268 |
| D08 | Mixed constructions, multicore networks | R169 |
| D09 | Conduits, fills, trenches, backfill, duct banks, HDD/casings with verified T4 | R174–R176, R272–R273 |
| D10 | Mutual heating and equivalent bank modelling | R172 |
| D11 | IEC 60853 cyclic and emergency, 24-h profile, four-node transient | R171 (loading) — cyclic rating is part of underground ampacity |
| D12 | 2-D finite-difference soil field, zones, dry-out, convergence | R170 |
| D13 | Route and crossing segment bottlenecks; HDD/casing | R169, R174 |
| D14 | Sensitivity, inverse design, optimisation (soil rho, spacing, cable/duct position) | R166, R172 (design aids); Section 65 opportunity register |
| D15 | Harmonic conductor heating | R169 (losses); harmonic analysis owner is Fault_Current_Studio (R350) |
| D16 | Manufacturer/NEC ampacity comparison only for matched conditions; code vs thermal separate | Section 37 |
| D17 | Traceable reports; JSON/CSV/XLSX/PDF without silent truncation | Sections 33, 77–78 |
| D18 | Ten original example regressions + 537 reference checks retained | Section 68 golden tests |
| D19 | Cable thermal IEC 60287 full model, cyclic/emergency, NEC/Neher–McGrath separate (from the earlier Fault_Current_Studio documents) | Group 8 (R165–R185), R257–R260 |
| D20 | Cable thermal: use the original v3.6.2 engine only after audit; no simplified replacement (from the earlier Production_Calculator documents) | Group 8 |
| D21 | MV cable shield/sheath grounding: single-point, both-ends, cross-bonding, induced voltage, circulating current, shield withstand (from the earlier Grounding_Calculator documents) | R183, R264–R268 |
| D22 | Duct spacing and conduit bank arrangement (from the earlier Vault_Calculator documents) | R174 (duct-bank configuration) |

### 2.3 Engineering method and verification requirements (Master Prompt Part 7)

Apply Master Prompt Section 37 in full, plus:

- Independent checks against published IEC 60287 worked examples and (where licensed) IEC TR 62095 / CIGRE benchmarks; the existing 540 synthetic cases are self-consistency, not validation.
- Convergence: mesh/domain/timestep studies for the 2-D and transient engines, with energy balance.
- Input sufficiency rules: no rating without construction, geometry and soil data; fail closed.
- Unit round-trip tests (ft/in ↔ m/mm, °F ↔ °C, K·m/W) — existing rule.
- The original React build (Gate 1) and parity (Gate 2) must be resolved or formally superseded by the owner before claiming platform parity.


### 2.4 Shared engines and connections to other calculators (Sections 23, 45, 49)

- **Owns:** underground cable thermal engine (steady state, cyclic/emergency, 2-D field), the shared duct-bank/underground thermal engine (R175, R176, R272, R273), sheath-bonding loss paths (one bonding engine shared with MV_Electrical_Design).
- **Uses:** pulling engine from Cable_Tray (R180–R182); fault current and clearing time from Fault_Current_Studio (R178); cable constructions from the Master Database; supplied soil data from the project.
- **Gives:** ampacity and conductor temperatures to DC_Cable_Connector, Inverter_LV_AC and MV_Electrical_Design; heat handoff to Vault_Calculator; schedules to Documentation_Schedules_QA.
- **Replaces:** the thermal copies inside Production and Fault_Current_Studio.

| Direction | Data | From / to |
|---|---|---|
| In | Cable constructions (layers, R20, α, screens, armour) | Master DB |
| In | Supplied soil thermal resistivity, earth temperature | Project inputs (owner) |
| In | Circuit loads and load profiles | the DC calculators (PV_String_MPPT, DC_Protection_Combiner, DC_Cable_Connector) / the LV AC calculators (Inverter_LV_AC, LV_Interconnection_Metering) / the MV calculators (MV_Electrical_Design, Transformer_POI) |
| In | Fault current, clearing time | Fault_Current_Studio |
| In | Duct-bank geometry, pulling results | Cable_Tray_Calculator / Vault reference |
| Out | Underground ampacity and temperatures per circuit | the DC calculators (PV_String_MPPT, DC_Protection_Combiner, DC_Cable_Connector) / the LV AC calculators (Inverter_LV_AC, LV_Interconnection_Metering) / the MV calculators (MV_Electrical_Design, Transformer_POI) cable sizing (STALE-tracked) |
| Out | Thermal handoff results for vaults | Vault_Calculator |
| Out | Underground cable and duct-bank schedules | Documentation_Schedules_QA_Calculator (R184, R185, R407) |

Every connection is a typed, versioned contract; a changed upstream result marks this calculator's dependent results STALE.


## 3. Work already done

**Status:** public site `https://headless-vmwfmgemqxl-classroomsolar-140e.wix-site-host.com/` (+ `/compare.html`), Wix site ID `9ae05e15-0791-4a48-9bd3-5e90ae03a68e` — a 154-file static release. An original private React/TypeScript v3.6.2 application holds the fuller engines (its production build was never verified). Use the live site code and the v3.6.2 engine source as the starting point.

**Functions already built (verify each):** steady-state ampacity and conductor temperature with resistance feedback; IEC 60287 loss paths (R20 and α, AC skin/proximity, dielectric, screen/sheath, armour, T1/T2/T3, external T4); direct-buried single-core; trefoil, flat, vertical and custom coordinates for up to 20 circuits; coupled image-source mutual heating with unequal loads; AC 1PH/3PH and DC; parallel sets with verified sharing or worst-set factor; single-point/both-ends/cross-bonding sheath losses; screening concentric solid-filled conduit; banks, backfill, air-filled ducts and HDD/casing only with a verified external T4; IEC 60853-oriented four-node cyclic and emergency transient (24-hour profile, emergency scan); 2-D finite-difference soil field with zones, heat sources, dry-out and convergence; route segments, crossings and bottleneck; sensitivity, inverse design (maximum soil resistivity, minimum spacing) and duct-position optimisation; harmonic conductor heating; manufacturer/code comparison only for matched conditions; measured-vs-predicted comparison with supplied data (MAE/RMSE); custom cable library with import/export and provenance; candidate ranking and code comparison page; feet/inches default with m/mm toggle; JSON/CSV/print exports. A separate earlier Neher–McGrath duct-bank calculator (up to 30 positions in 5×6 rows/columns, two-zone soil, AC/DC, voltage drop, imperial units) also exists — rebuild its duct-bank function on the website.

**Reference test fixture (not a real installation):** 1000 kcmil Al, 15 kV cable, 3-phase 13.8 kV 60 Hz, trefoil, single-point bonded; 500 A load; 25 °C earth; 90 °C limit; 1.0 K·m/W soil; 0.939165 m depth; OD 0.04953 m; R20 = 0.0000569 Ω/m; α = 0.00403/°C → **692.220438564634 A** continuous ampacity and **55.20790930550635 °C** at 500 A (T4 = 1.541570063174254 K·m/W, total heat 49.967131120695406 W/m). Corrected emergency screening: 2 h emergency at 50 A steps → 950 A PASS / 1000 A LIMIT. Keep the 10 example cases and 537 reference checks as regression tests; 540/540 synthetic cases and 3,600/3,600 comparisons are self-consistency only.

**Method references used so far:** Neher & McGrath (AIEE 1957); IEC 60287-1-1 and 60287-2-1; Aleksic et al. (plastic-duct U/V/Y constants); Brakelmann et al. (backfill/duct-bank equivalent); El-Kady (geometric factor for non-square banks — not yet implemented); Sellers & Black; Anders (Rating of Electric Power Cables); IEEE 835 (loss factor); Kennelly image method.


## 4. Functions still to be added

- [ ] R174–R176 and R272–R273 verified duct-bank and concrete-encased thermal engine on the website (rows × columns, occupied positions, two-zone soil), with validity limits (including envelope aspect ratio; El-Kady factors for elongated banks).
- [ ] R177 underground conduit fill (with the Cable_Tray conduit-fill engine).
- [ ] R178 short-circuit withstand using fault current and clearing time from Fault_Current_Studio.
- [ ] R179 underground cable voltage drop (shared conductor engine).
- [ ] R184 underground cable and duct-bank schedule; R185 trench cable allocation and arrangement documentation.
- [ ] R183 MV shield and bonding checks, shared with MV_Electrical_Design (one bonding engine).
- [ ] Above-ground cable thermal method (tray, conduit in air, free air) with its own verified standard method.

**Requirements with no implementation yet (build new):**

- [ ] R179 Underground cable voltage-drop calculation
- [ ] R184 Underground cable and duct-bank schedule
- [ ] R185 Trench cable allocation and electrical arrangement documentation

## 5. Earlier work still to be completed

- [ ] Bring the React v3.6.2 engines and the public-site engines into one versioned thermal engine package on the website; reach full parity (20-circuit and geometry editing, 2-D mesh/domain settings, scenario editor, study round-trip).
- [ ] Export existing browser-local studies and custom cables before migration (they live only in visitors' browsers).
- [ ] Replace the copies of thermal logic in other calculators (Production, Fault_Current_Studio, Grounding) with calls to this engine.
- [ ] Reconcile this calculator's 93-sheet database revision into the Master Database v13.

**Partly built — complete them:**

- [ ] R174 Duct-bank configuration design
- [ ] R175 Duct-bank electrical thermal calculation
- [ ] R176 Concrete-encased duct-bank thermal assessment
- [ ] R178 Underground cable short-circuit withstand assessment

**Built earlier — rebuild/carry over to the website and prove with tests:**

- [ ] R165 Underground cable configuration assessment
- [ ] R166 Underground cable spacing calculation
- [ ] R167 Trefoil cable arrangement assessment
- [ ] R168 Flat cable arrangement assessment
- [ ] R169 Underground cable ampacity calculation
- [ ] R170 Soil thermal-resistivity-based cable thermal assessment using supplied data
- [ ] R171 Underground ambient and installation-condition derating
- [ ] R172 Multiple-circuit thermal derating
- [ ] R173 Direct-buried cable suitability assessment
- [ ] R183 MV shield and bonding arrangement checks

**Logic exists in another calculator — integrate one engine, do not copy:**

- [ ] R177 Underground conduit-fill calculation
- [ ] R180 Underground cable-pulling tension calculation
- [ ] R181 Underground cable sidewall-pressure calculation
- [ ] R182 Underground cable bend-radius and pulling assessment

## 6. Checks and audits still to be done

- [ ] Published IEC 60287 worked examples and, where available, IEC TR / CIGRE benchmark cases; Neher–McGrath comparison kept separate from IEC.
- [ ] Mesh, domain and time-step convergence with energy balance for the 2-D and transient engines.
- [ ] Input-sufficiency guards: no rating without cable construction, geometry and soil data.
- [ ] Unit round-trip tests (ft/in ↔ m/mm, °F ↔ °C, K·m/W).
- [ ] Engineering and software audit; challenge campaign of 200 cases.
- [ ] Engineering audit (Section 72): methods, editions, equations, assumptions, units, correction factors, limits, source applicability, independent results, unsupported conditions, false PASS results.
- [ ] Software audit: logic, architecture, types, validation, error handling, edge cases, duplication, hard-coded values, feature preservation.
- [ ] Data audit: units, types, sources, revisions, duplicates, conflicts, missing values, overrides.
- [ ] Integration audit: schemas, IDs, dependencies, STALE results, unit and method compatibility with connected calculators.
- [ ] UI/UX audit: workflow, labels, units, help, warnings, responsiveness (desktop/tablet/mobile), WCAG 2.2 AA accessibility, diagram accuracy, persistence.
- [ ] Security audit: authentication, authorisation, private/public separation, secrets, input validation, dependencies.
- [ ] Requirements coverage audit: every ID in Section 2 traced to code and tests.
- [ ] Research register and benchmark matrix (Section 11): relevant calculators, manufacturer tools and papers actually reviewed (count only real sources).

## 7. Process to follow to finish everything

This is the Master Prompt V5.0 development process applied to this calculator. Follow it for every task.

### 7.1 Rules that never change (Master Prompt Sections 5, 6, 27, 34)
- Never invent a standard, clause, formula, coefficient, equipment rating, curve, clearing time, test result or repository state. Missing critical input → **INPUT REQUIRED**; never a guessed value.
- Every numerical result comes from a deterministic, tested calculation engine — never from AI text.
- Every result shows a status: PASS, FAIL, REVIEW REQUIRED, INPUT REQUIRED, NOT APPLICABLE, NOT VERIFIED, NOT SUPPORTED or STALE. Never PASS when inputs, sources, methods or validation are missing. Every warning says what is wrong, why it matters, which input to check and how to fix it.
- Never claim "complete", "100 %", "certified" or "compliant" without the evidence of Section 8 of this file.
- Preserve working calculations and verified results; change a validated method only with a documented reason and tests (Sections 52, 58).
- No paid service, subscription or usage-based dependency without the owner's approval (Section 84). No credentials, secrets or private data in code or Git (Sections 6, 60, 82).

### 7.2 Execution cycle for every task (Master Prompt Section 7)
**A Inspect** existing code, data, tests and behaviour → **B Research** primary standards, editions, manufacturer documents, papers and benchmark tools → **C Design** inputs, outputs, units, equations, sequence, error states, tests → **D Implement** the deterministic engine first, then UI, diagrams, data and integration, in small reversible changes → **E Test** (unit, golden, independent, boundary, invalid input, regression, UI, export, security, end-to-end) → **F Audit and fix** (separate engineering and software reviews; repeat until no critical/high defect) → **G Improve** (low-risk improvements; scope expansion only with approval) → **H Report** (files changed, tests run, results, limitations, next step). Do not stop after a plan, a draft or a good-looking screen.

### 7.3 Phases (Master Prompt Section 62)
| Phase | Work for this calculator | Done when |
|---|---|---|
| 0 Inventory (read-only) | Collect the live site code and the v3.6.2 engine source; inventory all engines and inputs; map R165–R185 and R272–R273. | Phase 0 report delivered: inventory, current state of every requirement with evidence, risks, batch plan, single best next task |
| 1 Engine | One versioned thermal engine package with contracts and input-sufficiency guards; duct-bank engine scope defined precisely. | Every engine has a master specification, version ID, typed contract and test harness, separate from UI |
| 2 Functional verification | Inputs, units, defaults, overrides, sequence, equations, intermediate values, invalid inputs, lookups, warnings, repeatability | All found defects fixed and retested |
| 3 Challenge and independent validation | Published worked examples, convergence studies, the 537 reference checks, challenge campaign. | Golden and independent checks pass within justified tolerances; real challenge-case count reported |
| 4 Customer workflow | Which inputs are visible, auto-filled from the database, inherited from other calculators, optional or advanced | Workflow specification written |
| 5 UX/UI | Trench and duct-bank cross-sections, thermal heat maps, cyclic plots drawn from engine data. | Screens use the shared design system; visuals come from the same data as the calculation |
| 6 Integration | Ratings to DC_Cable_Connector, Inverter_LV_AC and MV_Electrical_Design with STALE tracking; vault heat handoff to Vault_Calculator. | End-to-end tests pass; STALE tracking works |
| 7 Release | Staging and public-URL tests, monitoring, backup/restore, rollback | Owner approves the production release |

### 7.4 Engineering rules for every engine (Master Prompt Sections 28–33, 46–48)
- Before coding: master specification (purpose, inputs with units and sources, outputs, standard and edition, equations, assumptions, valid range, warnings, test cases) and data-dictionary entries with stable names (no "Value1", "Factor2").
- Engine: defined inputs/outputs/units, equations with variable definitions, source references (standard, edition, clause/table/equation), assumptions, valid range, input validation, numerical precision/convergence, version ID; identical results for identical inputs; handles zero/negative/huge/tiny/missing values; never shows a failed calculation as a normal result; separate from the UI.
- Units: one central unit service; SI internally; feet/inches and metric display; never mix units silently; full precision internally, round only for display.
- Assumptions classified CONFIRMED / DEFAULT / ENGINEERING ASSUMPTION / NEEDS USER CONFIRMATION / REFERENCE-DERIVED. Show DATABASE VALUE, USER OVERRIDE and VALUE USED IN CALCULATION for every overridable value, with an audit trail.
- Equipment data only from the Master Engineering Database (Section 44), auto-populated from the selected record, with the database revision stored with every result.
- Traceability chain for every important result: user input → database value → intermediate values → correction factors → equation/method → final result, with the limit used, status, warnings, sources and engine version.
- Results passed to other calculators go through typed, versioned contracts; changed upstream inputs mark downstream results **STALE** (Sections 47–50). Never propagate a result whose study case, topology, voltage level or assumptions do not match.

### 7.5 Testing rules (Master Prompt Sections 66–71)
- Golden tests with source of expected values; independent hand calculations or separate scripts (never only against code that shares the implementation); tolerances justified, never chosen to make a test pass.
- Boundary, invalid-input, unit-conversion, unsupported-case and regression tests; end-to-end tests for every applicable project type P1–P5.
- Challenge campaign toward **200 meaningful cases** designed to make the calculator fail; report the real number completed.
- Every reported defect: reproduce → trace UI → validation → lookup → calculation → result → saved state → fix the root cause → add a regression test → rerun all golden tests.

### 7.6 Working method
- GitHub is the home of the code (Section 60): tag the known-good state before work, feature branch, small commits, pull request for engineering/data/security changes, tests run before merge, tagged releases with rollback points.
- Work in controlled batches (Section 61); after each batch give the delivery report of Section 87 (requested, done, requirement IDs, preserved, files changed, sources, tests run with results, remaining gaps, next step).
- Keep these records up to date in the repository (Section 85): REQUIREMENTS.md (traceability for every ID in Section 2), MASTER_SPECIFICATION.md, DATA_DICTIONARY.md, DECISIONS.md, SOURCE_REGISTER.md, TEST_MATRIX.md, ISSUES.md, PROGRESS.md, CHANGELOG.md.
- Ask the owner only when a decision changes safety, correctness, scope, cost, privacy or is irreversible (Section 5). The only open items the Master Prompt leaves to the owner are: jurisdiction and code editions to target first, hosting provider and budget, which calculator becomes the first fully verified reference module, whether 35 kV stays the MV limit (Appendix F) — plus approval of production releases and paid services.

### 7.7 Calculator-specific rules carried over from the earlier documents
- Original private React site must stay owner-private (do not make it public to test)
- Feet/inches default display, m/mm toggle, SI internally; unit choice synchronised across pages and saved studies
- No certified claim without independent IEC/Neher–McGrath/manufacturer/field validation
- Fail closed: invalid geometry, missing evidence, unstable solutions
- No PASS from test fixtures, imported status or out-of-range methods; 500 A / 13.8 kV example is a fixture
- Ask for /workspace.html backup before migrations or destructive changes


## 8. Final result — what "finished" looks like

- One verified underground and duct-bank thermal engine on the website, used by every cable calculator, with steady-state, cyclic/emergency and 2-D field options and clear validity limits.
- All Group 8 requirements implemented, including schedules and trench documentation.
- Above-ground method available or clearly marked NOT SUPPORTED until verified.
- **Every requirement in Section 2** is implemented, or marked NOT APPLICABLE / NOT SUPPORTED with a written reason, with evidence in REQUIREMENTS.md (file, function, test). Status per requirement follows Section 57 (IMPLEMENTED — NOT VERIFIED → SOFTWARE TESTED → ENGINEERING VALIDATED → DEPLOYED → APPROVED).
- **Module completion checklist (Master Prompt Section 94) fully satisfied:** scope documented; existing behaviour preserved; methods and standard editions verified or flagged; deterministic engine separated from UI; inputs/outputs/units/assumptions/overrides/limits traceable; equipment data from the Master Database with revision recorded; golden and independent checks pass within justified tolerances; boundary, invalid-input, unsupported-case and regression tests pass; engineering and software reviews recorded; integration and STALE control work; UI and diagrams match the engine; reports and exports reproduce the screen; security and privacy satisfied; limitations disclosed; no known critical or high-severity defect.
- **Website acceptance (Section 95):** works on the public domain over HTTPS; its route opens directly and after refresh; desktop, tablet and mobile; private projects stay private; save/load/scenarios/recovery work; tested through the real public URL.
- **Reports and exports (Sections 77–78):** PDF calculation package, CSV, JSON (and schedules where applicable) containing inputs, units, equipment and database revision, method and standard edition, intermediate values, results with status, assumptions, warnings, sources and engine version — identical to the screen.
- **Honest status:** a final delivery report (Section 87) states exactly what is complete, what is not, and why.


## 9. Plugins and tools

| Capability (Master Prompt Section 8) | Use it for | Example plugin / tool |
|---|---|---|
| Git repository connector | Branches, commits, pull requests, issues, diffs | GitHub connector |
| Coding agent + execution environment | Write code, run builds and tests, debug | Coding agent with terminal (e.g. Claude Code / similar), Node.js, Python |
| Web research and browser | Official standards information, manufacturer datasheets, benchmark tool documentation | Web search, web fetch, browser |
| PDF / OCR document reader | Read code books, datasheets, manuals, papers page by page | PDF reader with OCR |
| Owner's document storage | The owner's books and reference PDFs (for example the NEC books kept in Dropbox) | Google Drive / Dropbox connector |
| Academic research search | Peer-reviewed papers and DOIs | Semantic Scholar / Google Scholar / IEEE Xplore search |
| Independent maths check | Hand-check equations and reference values | Python (NumPy, SciPy, SymPy), Wolfram |
| Browser / UI automation | End-to-end tests on desktop and mobile, downloads, console errors | Playwright (Chromium, Firefox, WebKit) |
| Accessibility check | WCAG 2.2 AA audit | axe-core / Lighthouse |
| UI / diagram design | Wireframes, screen flows, engineering diagrams | Figma or similar design tool |
| Database connector | Schemas, migrations, records, permissions | Connector for the chosen database |
| Hosting / deployment connector | Deployments, logs, domains, rollback | Connector for the chosen host (Wix connector only for the existing live sites) |
| Security analysis | Dependency, secret and code scanning | Dependabot / npm audit / pip-audit, CodeQL, secret scanning |

Use a tool only when it has a real role, check access/permissions/quota/cost first, never claim a tool ran when it did not (Sections 8–9). Do not use Formula Genius or Coursera. When delegation is available, split work into specialist reviews — standards, independent calculation, equipment data, code/architecture, UX, security, testing — and have an independent checker that never sees the builder's code (Section 9).

**Specific to this calculator:**

| Purpose | Tool |
|---|---|
| Thermal verification | Python NumPy/SciPy finite-difference scripts, Wolfram |
| Feature benchmarking only | CYMCAP, ETAP Cable Thermal documentation |

Benchmark tools are used to compare features and results only — never copy their code, data or methods without checking them (Section 12).


## 10. First task and first reply

1. Reply in Hinglish: confirm that Master Prompt V5.0 governs and that this is **Cable_Thermal_Calculator**; say what you can and cannot access.
2. Do Phase 0 only (read-only): inventory, current state of every requirement in Section 2 with evidence, risks, batch plan for Phases 1–3, and the single best next task.
3. Wait for the owner to approve the Phase 0 report, then work through Sections 4, 5 and 6 using the process of Section 7 until Section 8 is true.

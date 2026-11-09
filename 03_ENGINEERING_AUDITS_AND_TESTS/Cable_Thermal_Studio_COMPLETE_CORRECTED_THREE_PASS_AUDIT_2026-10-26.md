# Cable Thermal Studio — corrected complete input and source audit

**Audit date:** 26 October 2026  
**Scope:** The user's Cable Thermal Studio / underground cable thermal calculator work only. Do not combine unrelated solar-resource, MV switchgear, fault-current or PV production projects into this engineering input ledger.

## Three cross-check passes completed for this issue

**Pass 1 — exact original files:** Re-enumerated the primary ZIP, verified CRC integrity, compared SHA-256 and byte size of all 981 listed content files against the original `CONTENTS_SHA256.json`, verified the 982nd file is that manifest, and confirmed no duplicate or unlisted archived paths. Extracted and enumerated all original `.pdf`, `.png`, and `.svg` paths.

**Pass 2 — actual workbooks and source fields:** Read exact sheet names from `xl/workbook.xml` of the authoritative Excel workbook; compared all 93 names in sequence with public `data/manifest.json`, and checked each sheet's JSON exists in the public release. Verified workbook SHA-256. Opened all six companion workbooks and matched their 125 tab names against the earlier record. Ran `newStudy()` and `defaultField()` directly from archived JavaScript to verify 14 root properties, 14 continuous inputs, 55 settings, 13 control groups, 15 2-D field options, 9 zone keys, 6 heat-source keys, and 5 positioned-circuit keys.

**Pass 3 — written input ↔ PDF/image ↔ current website:** Matched the 39 collected user requirements with archived `docs/FINALIZED_SCOPE.md`, the original handover, current R42 web release (151 complete files), and exact media names. Read the four archived PDFs to identify whether they contained actual cable or site source measurements. The archive's reference report reproduces the original 500 A / 692.220438564634 A example, but **no PDF establishes a real project-specific manufacturer cable or installation**. Cross-checked 18 unanswered questions, 13 information categories, and 36 study categories.

**32/32 machine reconciliation checks passed.** There were no missing original archive files, mismatching master-workbook SHA-256 hashes, missing public worksheet JSONs, or unmatched original PDF/raster/SVG paths. The machine-readable record lists every individual check, the source archive hash, the workbook hash, and all exact names.

## Current protected baseline and correction ledger

- **Original engineering source:** `Cable_Thermal_Studio_Complete_2026-10-24.zip`, original private React/TypeScript v3.6.2 source and all 981 checksum-listed files (982 ZIP entries including the manifest).
- **Current tested public website:** `https://headless-vmwfmgemqxl-classroomsolar-140e.wix-site-host.com/`, published with the complete 151-file archive `Cable_Thermal_Studio_FINAL_PUBLIC_STABILIZATION_2026-10-25.zip`. It is separate from the uncompiled original React frontend.
- **Master:** `Engineering_Master_Database_Audited.xlsx`, SHA-256 `d38a19c7e28a4fe79d399d2ff498653b5febc5878d8ddafc155f888cc9855ba5`, 93 worksheets, 256,429 source rows and 53,117 formula texts as recorded in the matching public release manifest.
- **Display units:** feet/inches by default, switchable m/mm; calculations retain their canonical SI dimensions; real-site measurements have not been inferred from displayed demo values.
- **Physical project inputs:** no independently substantiated specific OEM cable datasheets, measured soil values, route drawings or field measurements were present in the identifiable transferred Cable Thermal Studio archive. Those values must not be filled using reference examples.
- **Original source numerical regression:** `500 A`, `13.8 kV`, `60 Hz`, `90°C`, `25°C` earth, `1 K·m/W` soil, `0.939165 m` center depth, `0.04953 m` OD, resulting in `692.220438564634 A` continuous illustrative ampacity and `55.20790930550635°C` at 500 A. This is an archived numerical test fixture, not a user-confirmed installation.
- **Archived PDFs:** `thermal-review-layout.pdf` is a one-page blank generic review template; `desktop_report_archived.pdf` and `mobile_report_archived.pdf` are one-page archival application-report captures; `generated_engineering_report_archived.pdf` is a two-page numerical example containing the test fixture. None supplies independent site-specific cable manufacturing evidence.
- **Extra JPGs in the Cable Thermal Calculator Library:** four identifiable project JPGs are explicitly marked `model_generated=true` in live Library metadata. The two older preview file names listed below have uncertain present availability/provenance; they have not been silently represented as user-uploaded drawings.
- **Other assistant-produced R-series screenshots and reports** are QA output, not extra files the user supplied as original cable-construction inputs.

## Key provenance guard

An archived QA report that says `PASS` shows what the archived application displayed for its **test conditions**; it does not prove IEC compliance, complete manufacturer/OEM input, a passed modern production build, or construction approval. The PDF and screenshot audit did not reveal credible independent real-site measurements. The user's engineering requirements must stay distinct from example-input defaults and previous assistant-generated release artifacts.

---

## Complete previously reconciled source register (verified again 26 October 2026)

### Prior verification method

1. **Written instructions:** matched recovered user instruction audit from the original 6–23 October chat and current conversation against the archived `docs/FINALIZED_SCOPE.md`.
2. **User-supplied source archive:** enumerated every file in the original `Cable_Thermal_Studio_Complete_2026-10-24.zip`; checked its `README_START_HERE.md`, six calculation workbooks, archived PDF/screenshots, React defaults and engineering-method documentation.
3. **Current authoritative assets:** matched live-release worksheet manifest with original workbook `xl/workbook.xml` worksheet names and all public source-data asset paths; checked original workbook SHA-256 and saved handover requirements and release reports.

**Archive count clarification:** The transferred original ZIP contains **982 file entries**: **981 archived content files listed and SHA-256-verified in `CONTENTS_SHA256.json`**, plus the `CONTENTS_SHA256.json` manifest itself. There are no duplicate ZIP member paths or unmanifested content files. This resolves the earlier 981-versus-982 count without losing a file.

**Verification results:** 93 of 93 Master worksheets agree in exact order; 256,429 records; 53,117 stored formula texts; 6 unique named companion workbooks with 125 sheets. All 93 source-worksheet JSON files are present. Workbook SHA-256 `d38a19c7e28a4fe79d399d2ff498653b5febc5878d8ddafc155f888cc9855ba5`. 4 PDFs, 9 PNG/JPEG images, 5 SVG assets in the supplied original archive. All exact filenames were listed twice from archive enumeration and compared to ZIP manifests.

**Provenance note:** The source archive contains testing/reporting PDFs and images, but an archived file is not automatically a separately uploaded manufacturer document or a user photograph. The archive does not establish a complete history of any pictures that appeared only inline in older chats. These distinctions are preserved below.

## Evidence and input-status cross-check (final review)

| Written source or requested item | Independently compared against | Audit conclusion |
| --- | --- | --- |
| Original app and no loss of existing work | Recovered v3.6.2 TypeScript source, original transfer ZIP, archived `FINALIZED_SCOPE.md` and SHA-256 file manifest | 981 content files preserved in the source ZIP; archive itself has 982 files including the manifest |
| Use the authoritative engineering Master Database | Exact workbook bytes, OpenXML 93 physical worksheets, current public `data/manifest.json`, all 93 JSON sheet paths | Exact workbook SHA-256, worksheet order and all worksheet record/formula counts match |
| All original engineering methods | Six companion `.xlsx` books and archived scope document | 125 tab names accounted for, complete names recorded below; availability does not alone establish every method is coded/certified |
| Complete input field coverage | `newStudy()` and `defaultField()` executed from recovered original source and compared with archived exact-field JSON | Root 14, base 14, settings 55, 13 control groups, 2-D field 15, zones 9, sources 6 and positioned-circuit 5 keys matched exactly |
| User-requested units and public access | Latest public HTML, unit synchronization scripts and public release/source register | Units/display and access requirement recorded; no site-specific cable-construction verification can be inferred from UI success |
| PDFs, reference images and drawings | Original 982-file ZIP extension list, ZIP manifest, Library project-media inventory and original design/QA paths | Four PDFs, nine PNGs and five SVGs in original ZIP, plus four generated Library JPGs; no OEM/site construction drawing independently identified |
| Actual project-specific design inputs versus bundled demo data | Reference example marker, original study object and archived scope | The numerical example is **a test fixture**. User-specific installation dimensions, thermal property measurements, equipment drawings and duty profiles are not established as a field project |
| Formerly shared inline media | Current user-uploaded media listing, Library folder and recovered ZIP | The named archived and Library items are inventoried. Any historical inline-only images not retained in a file/archive cannot be proved present or absent |

**Do not mix separate workstreams:** Solar resource production, Heber 2 communication/switchgear, SunDrum and other PV project attachments are not input files for this Cable Thermal Studio audit. They have not been silently inserted into cable-calculation assumptions.

**File provenance:** PDFs/screenshots in the archived source are mostly design/QA outputs; the project image folder contains generated JPGs. Neither category may be represented as a verified user-supplied equipment drawing or field measurement. Actual manufacturer/model/source-file attribution requires explicit evidence.

## Related calculator-suite instructions relevant to this site (not thermal input measurements)
- Cable Thermal Studio belongs to a broader engineering-calculator suite discussed in prior work: **22 calculator families (five existing and 17 proposed), with a stated 106 functional modules**. Those other calculators are **not** silently imported into this cable-only audit.
- Where technically useful, ChatGPT and Google AI Studio were requested to improve calculator assistance, research and UX. Their output must not substitute for deterministic cable thermal equations or verified source values.
- Product designs and manufacturer calculator workflows are reference examples for interface and validation ideas; this does not authorize copying proprietary sources or assuming missing manufacturer ratings.
- The latest explicit access requirement for this specific calculator is a **simple public URL available to anyone**. Earlier private-team access requirements for the broader calculator suite should not override that later instruction.

## A. Written instructions and project inputs recorded
### Project and continuity
1. Underground cable thermal/ampacity engineering calculator and companion database, not a replacement fault, grounding, tray, protection, voltage-drop, BOM or general-purpose calculator.
2. Keep the original Work-chat source and all old functioning calculations, tested numerical results, reference workbooks, cases, files, diagrams, user data and project history; no silent regression or data deletion.
3. Use the original v3.6.2 React/TypeScript source as the engineering baseline and keep the public Wix implementation available until genuine tested replacement is possible.
4. One simple public URL accessible to anyone without a ChatGPT account; do not replace the existing working site with a different unrelated app.
5. Finish requested implementation with actual verification, not repetitive version increments or unproven completion claims.
6. Use all useful connected tools/plugins when justified, but do not use Formula Genius or Coursera for this project.
7. Preserve safe backups, full original-source copies, SHA/integrity manifests, rollback packages and a central requirements/continuation record.

### Inputs, units and user experience
1. Default all displayed geometric distances to US feet/inches; provide selectable metric m/mm, with correct conversion both ways and canonical SI internally.
2. Keep unit preference synchronized across every calculator page and saved study; do not reinterpret old SI records as US values.
3. Fix text/controls/tables/legends/long references and report content overflowing assigned UI containers at mobile, tablet and desktop widths; shrink fonts or wrap/scroll appropriately.
4. Clean, professional, responsive workflow with clear inputs, outputs, charts, physical cross-sections and readable status/assumption messages.
5. Allow manual cable construction and database-record selection; do not invent missing equipment properties from names.
6. Support new/edit/delete custom cables, Excel/CSV/JSON import/export, preview, validation, provenance, duplicate ID protection and source audit.
7. Save/reopen/copy/delete/export complete browser-local studies; migrate legacy cases without losing numeric meaning; clear stale outputs and never trust imported approval flags.
8. Provide one secure, merged, integrity-checked workspace backup for saved studies and custom cables; prevent data loss on storage failures.
9. Provide searchable records for all 93 audited Master Database worksheets and preserve formulas, provenance, manufacturer references, original field names and full exports.

### Steady and construction physics
1. Continuous ampacity, conductor temperature, load vs current-rating, margins, convergence and PASS/FAIL/review hierarchy.
2. IEC 60287-oriented loss and heat-flow paths: conductor temperature dependence, R20, AC skin/proximity, dielectric, screen/sheath, armour, T1/T2/T3 and external T4.
3. Direct-buried single-core, trefoil/flat/vertical/custom phase arrangement, physical spacing, burial depth, multiple circuits and unequal loads.
4. Explicit electrical system (three-phase AC, single-phase AC, DC), voltage rating, frequency, active conductors within cable, parallel sets and current-sharing evidence.
5. Sheath bonding and circulating losses, single-point/both-ends/cross-bonding; magnetic/nonmagnetic armour paths and verified limits.
6. Mixed cable constructions and balanced multicore thermal networks, different cable heat factors and each conductor temperature limit.
7. Screened conduits, solid/air fills, walls, trenches/backfill, duct banks, casings/HDD and shared banks with verified equivalent exterior thermal data.
8. Physical mutual heating, cable position and equivalent bank modeling, with documented model applicability.

### Advanced analyses and studies
1. IEC 60853-oriented cyclic and emergency transient modeling, 24-hour load profile, real simulation duration, thermal masses, timestep refinement and stable initial equilibrium.
2. Four-node transient, emergency current scan, exact event timing and periodic-convergence checks.
3. 2-D finite-difference soil thermal field, multiple sources, backfill rectangles, nonuniform soil, dry-out transitions and mesh/domain convergence diagnostics.
4. Route and crossing segment ampacity/bottleneck analysis; separate HDD/casing special-installation inputs.
5. Parameter sensitivity, environmental envelope, route comparisons, inverse allowable soil resistivity/spacing and candidate cable/duct-position optimization.
6. Harmonics and frequency-specific conductor heating, with explicit spectrum and AC resistance multipliers.
7. Independent manufacturer/NEC ampacity comparison only where cable identity and actual conditions match; code versus thermal criteria separated.
8. Measured-versus-predicted temperature validation with MAE, RMSE and maximum error by channel.
9. Independent IEC/IEEE/Neher–McGrath, published manufacturer, benchmark, or field validation before certified claims.

### Results, reporting and QA
1. Traceable numerical inputs, assumptions, equations/model version, thermal resistance paths, uncertainties and source references in the report.
2. Full JSON/CSV/XLSX study and source exports, safe spreadsheet content, no arbitrary silent row truncation, clean native PDF/print pages.
3. Ten original example-case regressions plus original 537 retained reference checks; preserve all old passing cases and expand automated tests for new methods.
4. Fail closed for invalid geometry, material properties, missing electrical/screen/duct evidence, unstable temperature solutions or unknown selector values.
5. No project-approval PASS from test fixtures, imported JSON status, generic catalogue name, or an approximate method outside its stated limits.
6. Browser-mobile validation, real functionality/print QA, source-workbook formula mapping, source checksum comparison, release acceptance and rollback.

## B. Project documents, workbook and source files provided
1. Cable_Thermal_Studio_Complete_2026-10-24.zip — primary complete transferred source, public rebuild, archived engine, evidence and workbooks.
2. Cable_Thermal_Studio_PUBLIC_RELEASE_2026-10-24.zip — separately provided public release package.
3. Underground_Cable_Thermal_WebApp_COMPLETE.zip — older Python/FastAPI source/reference archive.
4. Engineering_Master_Database_Audited.xlsx — authoritative 93-sheet master workbook.
5. Underground_Cable_Thermal_Calculator_MAIN_FINAL.xlsx — main steady-state construction and cable-network workbook.
6. Underground_Cable_Thermal_Calculator_TRANSIENT_FINAL.xlsx — emergency/cyclic worksheet.
7. Underground_Cable_Thermal_Calculator_FIELD2D_FINAL.xlsx — 2-D soil-field workbook.
8. Underground_Cable_Thermal_Calculator_ROUTE_OPTIMIZATION_FINAL.xlsx — route, sensitivity and design selection (included within original source archive).
9. Underground_Cable_Thermal_Calculator_HARDENING_VALIDATION_FINAL.xlsx — harmonics, envelope, manufacturer and measured-temperature checks (included within original source archive).
10. Underground_Cable_Thermal_Calculator_RELEASE_CONTROL_FINAL.xlsx — release and model-validity controls (included within original source archive).
11. Engineering_Master_Database_FINAL.xlsx — preserved historical master snapshot embedded in original archive; not a replacement for the audited master.
12. Underground_Cable_Calculator_Support.zip — historical Library-recorded support package; the historical audit did not establish its exact user-upload relationship in this project.
13. Underground_Cable_Calculator.xlsx — historical Library-recorded input workbook; not part of the seven mounted direct inputs.

**Mounted direct conversation transfer files:** Cable_Thermal_Studio_Complete_2026-10-24.zip, Cable_Thermal_Studio_PUBLIC_RELEASE_2026-10-24.zip, Engineering_Master_Database_Audited.xlsx, Underground_Cable_Thermal_Calculator_FIELD2D_FINAL.xlsx, Underground_Cable_Thermal_Calculator_MAIN_FINAL.xlsx, Underground_Cable_Thermal_Calculator_TRANSIENT_FINAL.xlsx, Underground_Cable_Thermal_WebApp_COMPLETE.zip.

## C. Included numerical example (test fixture, not a verified real installation)

The recovered source explicitly labels this record **Reference example**. It must not be silently substituted for a real project:
- **Electrical:** 1000 kcmil aluminium, 15 kV nameplate cable; AC 3-phase, 13.8 kV operating voltage, 60 Hz, one parallel set, single-core and single-point bonded reference selection.
- **Load/temperature:** 500 A example load; 25°C reference earth temperature; 90°C conductor limit.
- **Soil/geometric:** 1.0 K·m/W native soil; 0.939165 m cable-center burial depth; 0.04953 m cable OD; 0.02926 m conductor diameter; 0.04044 m insulation OD; 0.043 m sheath diameter; trefoil formation.
- **Heat/resistance:** R20=0.0000569 Ω/m; α=0.00403/°C; AC factor=1.0251328070572212; dielectric=0.004114251237296077 W/m; T1=0.18025777365930096 K·m/W, T2=0, T3=0.09186124885560788 K·m/W; reference mutual factor=2.2377027287708477.
- **Reference output:** 692.220438564634 A continuous ampacity and 55.20790930550635°C conductor temperature at 500 A, with source method assumptions.
- **Examples in other modules:** 24 hourly cyclic load ratios; 2-hour emergency and 24-hour cyclic regression; model-specific reference conditions for numerical verification, not provided as construction approval.

## D. Calculator engineering input fields available in recovered source
1. **Circuit identity and electrical load:** project/study name; cable ID/label/source; cable voltage rating; reference-example flag; circuit/set labels; AC 1PH/3PH or DC; line voltage; frequency; total demand/load current; individual circuit load current; parallel set count; allocation/sharing mode; worst-set sharing multiplier; per-set measured currents; sharing source; active rows; rating basis and fixed-neighbor/all-scaled selection.
2. **Cable construction and electrical losses:** conductor material/size, number of loaded cores, conductor diameter and cable OD, insulation OD and thermal resistivity, sheath/screen mean diameter, jacket thermal resistivity, R20, conductor α20, measured or derived AC resistance factor, skin ks, proximity kp, relative permittivity, capacitance, dielectric loss tangent and W/m, sheath loss factor λ1, armour loss factor λ2, screen R20 and α, bonding mode, armour type, metallic loss source.
3. **Cable internal/external thermal properties:** T1, T2, T3, dielectric internal resistance, external T4, T4 source and validity basis, environment source; installation and thermal model selectors; geometry validity/verified-source checkboxes.
4. **Installation geometry and conditions:** burial depth to centerline, cable/circuit horizontal X, vertical depth and arrangement, phase spacing, circuit rows up to 20, soil thermal resistivity, ambient earth temperature, mutual-heating multiplier, physical positions, separate spacing and backfill/trench boundaries.
5. **Conduit, bank and HDD:** conduit/duct inside/outside diameter, duct wall thermal resistivity, duct fill thermal resistivity, gap/air heat-transfer coefficients, filled or air duct, duct bank rows/columns and occupied positions, duct spacing/depth, solid conduit/concrete or HDD/casing, independently verified T4 and source.
6. **Time-dependent:** 24 hourly relative load multipliers, base load current, emergency peak current and duration, time step in minutes, simulation days, number of iterations, conductor area/diameter, insulation OD, volumetric conductor/insulation/shell/soil heat capacities, soil participation and comparison tolerance.
7. **2-D soil field:** domain width/depth, mesh node counts X/Y, 2-D heat sources (X/Y,W/m), zone rectangles and zone thermal resistivities, native and dry-soil resistivity, dryout threshold, relaxation omega, convergence tolerance, iteration counts, dryout passes, active flags and source coordinates.
8. **Routes, scenarios and selection:** route segment name/length/installation/depth/soil/environment/current/external T4/source; sensitivity variable/sample list; inverse min/max soil rho, margin, circuit spacing scan min/max/step; optimization sets, candidate cable IDs, phase spacing multiplier, maximum sets, duct position and grouping; alternative scenario override records.
9. **Harmonics, manufacturer and field:** harmonic order, current, Rac harmonic multiplier and source; manufacturer/model/reference ampacity and matching ambient/temperature/soil/depth/installation/grouping; code table/edition/base ampacity/four factors and provenance; field measurement source, sensor/channel, measured and predicted temperature and error threshold.
10. **Release evidence and reports:** verified cable/environment/method flags, equivalent-network source/verification, source workbook/sheet and product/manufacturer citations, per-module status, project assumptions, case JSON, CSV/XLSX/PDF export, locally stored study ID, input signature, stale-result guard and backup checksum.

These are fields the software can accept or model, **not evidence that the user supplied an actual project value for every field**.

## E. All PDFs in the user-supplied original archive
1. `01_Private_Site_v3.6.2_Source/docs/design/thermal-review-layout.pdf`
2. `04_QA_Evidence/Browser_Archive_QA/desktop_report_archived.pdf`
3. `04_QA_Evidence/Browser_Archive_QA/generated_engineering_report_archived.pdf`
4. `04_QA_Evidence/Browser_Archive_QA/mobile_report_archived.pdf`

No separate user-uploaded cable-thermal manufacturer/IEC PDF was identifiable from the mounted original-transfer files or the reviewed Cable Thermal Calculator Library folder. These four PDFs are archived design and testing/reporting files included inside the supplied ZIP.

## F. All raster images in the user-supplied original archive
1. `01_Private_Site_v3.6.2_Source/docs/design/master-database-explorer.png`
2. `01_Private_Site_v3.6.2_Source/docs/design/thermal-review-layout.png`
3. `04_QA_Evidence/Browser_Archive_QA/desktop_report_archived.png`
4. `04_QA_Evidence/Browser_Archive_QA/desktop_steady_archived.png`
5. `04_QA_Evidence/Browser_Archive_QA/desktop_transient_archived.png`
6. `04_QA_Evidence/Browser_Archive_QA/generated_engineering_report_archived.png`
7. `04_QA_Evidence/Browser_Archive_QA/mobile_report_archived.png`
8. `04_QA_Evidence/Browser_Archive_QA/mobile_steady_archived.png`
9. `04_QA_Evidence/Browser_Archive_QA/mobile_transient_archived.png`

### SVG assets in the same source archive
1. `01_Private_Site_v3.6.2_Source/docs/design/master-database-explorer.svg`
2. `01_Private_Site_v3.6.2_Source/public/favicon.svg`
3. `01_Private_Site_v3.6.2_Source/public/file.svg`
4. `01_Private_Site_v3.6.2_Source/public/globe.svg`
5. `01_Private_Site_v3.6.2_Source/public/window.svg`

### Additional project-associated images in Library
- `/Cable Thermal Calculator/cable-thermal-audit-1791380438913.jpg` — Library metadata marks this **generated**, not conclusively user-uploaded.
- `/Cable Thermal Calculator/cable-thermal-studio-1791310869052.jpg` — Library metadata marks this **generated**, not conclusively user-uploaded.
- `/Cable Thermal Calculator/cable-thermal-studio-v3-1791366797928.jpg` — Library metadata marks this **generated**, not conclusively user-uploaded.
- `/Cable Thermal Calculator/cable-thermal-v3-2-1791570830247.jpg` — Library metadata marks this **generated**, not conclusively user-uploaded.
- `Session04_Isotherm_Preview.png` — present in older Library inventory; current bytes and upload provenance not verified.
- `calculator-preview.png` — present in earlier Library inventory, recorded as moved to Trash; related preview also archived elsewhere.

QA screenshot and PDF files generated by the assistant in later R-series releases are **outputs**, not counted as new user-submitted input files.

## G. All 93 Master Database worksheets — exact workbook order
01. `CABLES` — 13,223 source rows; 90 fields; 0 formula texts
02. `CABLE_TYPES` — 797 source rows; 13 fields; 0 formula texts
03. `TRANSMISSION_CONDUCTORS` — 1,610 source rows; 32 fields; 0 formula texts
04. `PV_MODULES` — 26,000 source rows; 27 fields; 0 formula texts
05. `BATTERIES` — 865 source rows; 15 fields; 0 formula texts
06. `BATTERY_PERFORMANCE` — 10,532 source rows; 9 fields; 0 formula texts
07. `TRANSFORMERS` — 1,201 source rows; 34 fields; 0 formula texts
08. `MOTORS_NAMEPLATE` — 1,162 source rows; 42 fields; 0 formula texts
09. `MOTOR_CHARACTERISTICS` — 2,040 source rows; 7 fields; 0 formula texts
10. `MOTOR_MODELS` — 186 source rows; 6 fields; 0 formula texts
11. `HV_BREAKERS` — 3,305 source rows; 30 fields; 0 formula texts
12. `HV_BREAKERS_EXTENDED` — 3,476 source rows; 7 fields; 0 formula texts
13. `LV_BREAKERS` — 50,524 source rows; 18 fields; 0 formula texts
14. `FUSES` — 22,271 source rows; 26 fields; 0 formula texts
15. `RELAYS` — 8,914 source rows; 22 fields; 0 formula texts
16. `RECLOSERS` — 3,267 source rows; 24 fields; 0 formula texts
17. `TRIP_DEVICES` — 17,889 source rows; 7 fields; 0 formula texts
18. `OVERLOAD_HEATERS` — 5,776 source rows; 5 fields; 0 formula texts
19. `ELECTRONIC_CONTROLLERS` — 1,709 source rows; 7 fields; 0 formula texts
20. `CSD_DEVICES` — 2,575 source rows; 8 fields; 0 formula texts
21. `RELIABILITY` — 98 source rows; 10 fields; 0 formula texts
22. `RELIABILITY_EXTENDED` — 141 source rows; 6 fields; 0 formula texts
23. `FIRE_PROTECTION` — 25 source rows; 9 fields; 0 formula texts
24. `CONDUIT_FIRE_PROTECTION` — 7 source rows; 9 fields; 0 formula texts
25. `HARMONICS` — 445 source rows; 5 fields; 0 formula texts
26. `RECTIFIERS` — 379 source rows; 9 fields; 0 formula texts
27. `INTERRUPTION_COST` — 30 source rows; 5 fields; 0 formula texts
28. `RAILWAY_LOADS` — 7 source rows; 7 fields; 0 formula texts
29. `IBR` — 641 source rows; 36 fields; 0 formula texts
30. `SWITCHGEAR` — 114 source rows; 19 fields; 0 formula texts
31. `INSTRUMENT_TRANSFORMERS` — 546 source rows; 17 fields; 0 formula texts
32. `DISCONNECTS` — 186 source rows; 18 fields; 0 formula texts
33. `CONDUCTOR_MATERIALS` — 2 source rows; 11 fields; 0 formula texts
34. `CONDUCTOR_SIZES` — 30 source rows; 4 fields; 0 formula texts
35. `CABLE_SC_K_FACTORS` — 8 source rows; 6 fields; 0 formula texts
36. `INSULATION_CLASSES` — 5 source rows; 8 fields; 0 formula texts
37. `GROUND_ELECTRODES` — 109 source rows; 18 fields; 0 formula texts
38. `NEUTRAL_GROUNDING_RESISTORS` — 88 source rows; 18 fields; 2 formula texts
39. `SURGE_ARRESTERS` — 103 source rows; 19 fields; 0 formula texts
40. `CABLE_TRAYS` — 95 source rows; 25 fields; 0 formula texts
41. `CABLE_CLEATS` — 152 source rows; 15 fields; 0 formula texts
42. `BOX_FILL` — 7 source rows; 6 fields; 0 formula texts
43. `CONDUITS` — 24 source rows; 11 fields; 0 formula texts
44. `ENCLOSURES` — 156 source rows; 21 fields; 0 formula texts
45. `PROTECTION_CURVES` — 5 source rows; 11 fields; 0 formula texts
46. `SOURCE_REGISTER` — 2,280 source rows; 12 fields; 0 formula texts
47. `TERMINATIONS` — 1,000 source rows; 18 fields; 0 formula texts
48. `AMPACITY_ROUTES` — 28 source rows; 9 fields; 0 formula texts
49. `AMPACITY_AMBIENT_FACTORS` — 15 source rows; 7 fields; 0 formula texts
50. `AMPACITY_CCC_FACTORS` — 7 source rows; 3 fields; 0 formula texts
51. `AMPACITY_PARAMETERS` — 14 source rows; 3 fields; 0 formula texts
52. `NEC_AMPACITY_2020` — 1,524 source rows; 15 fields; 0 formula texts
53. `NEC_AMPACITY_2023` — 1,524 source rows; 15 fields; 0 formula texts
54. `GENERATORS` — 17 source rows; 18 fields; 0 formula texts
55. `MOTOR_LOCKED_ROTOR_CODES` — 19 source rows; 11 fields; 0 formula texts
56. `CABLE_FAULT_CURRENT_REFERENCE` — 21 source rows; 14 fields; 0 formula texts
57. `CABLE_TRAY_EQUIPMENT` — 124 source rows; 18 fields; 0 formula texts
58. `TRAY_EXPANSION_RULES` — 13 source rows; 6 fields; 0 formula texts
59. `CABLE_CLEAT_SIZES` — 123 source rows; 8 fields; 0 formula texts
60. `CABLE_CLEAT_SIZE_MAP` — 722 source rows; 5 fields; 0 formula texts
61. `TRAY_ACCESSORY_RULES` — 53 source rows; 9 fields; 0 formula texts
62. `CABLE_PLANNING_DEFAULTS` — 10 source rows; 18 fields; 0 formula texts
63. `NEC_TRAY_FILL` — 24 source rows; 10 fields; 0 formula texts
64. `NEC_CHANNEL_TRAY_FILL` — 6 source rows; 7 fields; 0 formula texts
65. `TRAY_ENGINEERING_DEFAULTS` — 5 source rows; 5 fields; 0 formula texts
66. `CABLE_IMPEDANCE_DEFAULTS` — 9 source rows; 8 fields; 0 formula texts
67. `TRAY_EGC_METAL_AREA` — 9 source rows; 7 fields; 0 formula texts
68. `EGC_SIZE_BY_OCPD` — 21 source rows; 5 fields; 0 formula texts
69. `EGC_SIZE_THRESHOLDS` — 21 source rows; 5 fields; 0 formula texts
70. `TRAY_EGC_AREA_THRESHOLDS` — 10 source rows; 5 fields; 0 formula texts
71. `TRAY_WIDTH_CODES` — 7 source rows; 4 fields; 0 formula texts
72. `TRAY_BARRIER_COVER_CODES` — 4 source rows; 5 fields; 0 formula texts
73. `TRAY_GROUNDING_ACCESSORIES` — 14 source rows; 7 fields; 0 formula texts
74. `PARTS_CATALOG` — 744 source rows; 27 fields; 0 formula texts
75. `BREAKER_LUGS` — 412 source rows; 34 fields; 0 formula texts
76. `PV_OPTIMIZERS` — 48 source rows; 17 fields; 0 formula texts
77. `CONDUCTOR_PROPERTIES` — 25 source rows; 17 fields; 0 formula texts
78. `LEGACY_NEC_REFERENCE` — 2,189 source rows; 6 fields; 0 formula texts
79. `SHEET_MAP` — 93 source rows; 10 fields; 0 formula texts
80. `FIELD_AUDIT` — 1,108 source rows; 15 fields; 0 formula texts
81. `DATA_ISSUES` — 3,483 source rows; 6 fields; 0 formula texts
82. `RESEARCH_GUIDANCE` — 24 source rows; 9 fields; 0 formula texts
83. `MODEL_REQUIREMENTS` — 63 source rows; 6 fields; 0 formula texts
84. `PV_UNIT_REVIEW` — 25,882 source rows; 13 fields; 0 formula texts
85. `PLUGIN_LOG` — 36 source rows; 5 fields; 0 formula texts
86. `CHANGE_LOG` — 23,007 source rows; 8 fields; 0 formula texts
87. `AUDIT_README` — 42 source rows; 2 fields; 0 formula texts
88. `OPTIMIZER_REVIEW` — 36 source rows; 21 fields; 0 formula texts
89. `DATABASE_TABLE_INDEX` — 78 source rows; 6 fields; 0 formula texts
90. `PAPER_AUDIT` — 106 source rows; 13 fields; 0 formula texts
91. `CALCULATOR_KEY_AUDIT` — 78 source rows; 9 fields; 0 formula texts
92. `CABLE_NORMALIZATION` — 10,621 source rows; 18 fields; 53,105 formula texts
93. `NUMERIC_BENCHMARKS` — 5 source rows; 5 fields; 10 formula texts

## H. Six companion workbooks — complete internal sheet-name inventory
### Underground_Cable_Thermal_Calculator_FIELD2D_FINAL.xlsx — 11 sheets
1. `SESSION4_OVERVIEW`
2. `FIELD_INPUTS_S4`
3. `FIELD_MAP_S4`
4. `CONDUCTANCE_S4`
5. `FDM_MOIST_S4`
6. `FDM_DRY1_S4`
7. `FDM_DRY2_S4`
8. `ISOTHERM_S4`
9. `S4_VERIFICATION`
10. `S4_SOURCES`
11. `S4_INTEGRATION_MAP`

### Underground_Cable_Thermal_Calculator_HARDENING_VALIDATION_FINAL.xlsx — 31 sheets
1. `S8_OVERVIEW`
2. `FROZEN_BASELINE`
3. `TOOLS_100`
4. `RESEARCH_100`
5. `ADAPTATION_BACKLOG`
6. `INPUT_GUARD_S8`
7. `ADAPTIVE_TEMP_S8`
8. `CASE_SIGNATURE_S8`
9. `DOMAIN_MESH_QA_S8`
10. `FIELD_VALIDATION_S8`
11. `STRESS_200`
12. `FAILURE_LOG`
13. `FIX_REGISTER`
14. `S8_DASHBOARD`
15. `S9_OVERVIEW`
16. `ROBUST_ENVELOPE_S9`
17. `CONVERGENCE_LAB_S9`
18. `HARMONIC_HEAT_S9`
19. `INPUT_STYLE_S9`
20. `REGRESSION_200_S9`
21. `S9_FAILURES_FIXED`
22. `S9_RELEASE_GATE`
23. `S10_OVERVIEW`
24. `PAPERS_TOP100_S10`
25. `CROSS_METHOD_S10`
26. `VALIDATION_MATRIX_S10`
27. `BENCHMARK_IMPORT_S10`
28. `FIELD_VALIDATION_PLAN_S10`
29. `MANUFACTURER_BENCHMARK_S10`
30. `S10_QA`
31. `S10_RELEASE_GATE`

### Underground_Cable_Thermal_Calculator_MAIN_FINAL.xlsx — 36 sheets
1. `START`
2. `EASY_INPUT`
3. `ADVANCED`
4. `CIRCUITS`
5. `RESULTS`
6. `IEC60287_ENGINE`
7. `MUTUAL_MATRIX`
8. `TRANSIENT_60853`
9. `SENSITIVITY`
10. `SCENARIOS`
11. `DESIGN_SOLVER`
12. `AMPACITY_COMPARE`
13. `THERMAL_VISUALS`
14. `OPTIMIZER`
15. `QA_RELEASE`
16. `DATABASE_CABLES`
17. `DATABASE_MATERIALS`
18. `DATABASE_CONDUITS`
19. `FORMULAS`
20. `HANDOFF`
21. `REPORT`
22. `REFERENCES`
23. `WORKBOOK_MAP`
24. `MASTER_SPEC`
25. `DATA_DICTIONARY`
26. `ASSUMPTIONS_LOG`
27. `CUSTOM_GEOMETRY`
28. `B1_GEOMETRY`
29. `MUTUAL_RTH_B1`
30. `COUPLED_SOLVER_B1`
31. `GOLDEN_TESTS`
32. `BATCH_LOG`
33. `CHANGE_LOG`
34. `B2_LOSS_ENGINE`
35. `METALLIC_LOSS_ENGINE`
36. `DEVELOPMENT_STATUS`

### Underground_Cable_Thermal_Calculator_RELEASE_CONTROL_FINAL.xlsx — 5 sheets
1. `START`
2. `MODULE_MAP`
3. `QA_SUMMARY`
4. `OPEN_GATES`
5. `CHANGE_CONTROL`

### Underground_Cable_Thermal_Calculator_ROUTE_OPTIMIZATION_FINAL.xlsx — 20 sheets
1. `SESSION5_OVERVIEW`
2. `CABLE_BASIS_S5`
3. `CROSSING_S5`
4. `HDD_CASING_S5`
5. `ROUTE_SEGMENTS_S5`
6. `ROUTE_RESULTS_S5`
7. `S5_VERIFICATION`
8. `S5_SOURCES`
9. `S5_INTEGRATION_MAP`
10. `SESSION6_OVERVIEW`
11. `CONTROL_PANEL_S6`
12. `SENSITIVITY_S6`
13. `SCENARIOS_S6`
14. `THERMAL_OPTIMIZER_S6`
15. `DUCT_POSITION_S6`
16. `DATA_PROVENANCE_S6`
17. `S6_DASHBOARD`
18. `S6_VERIFICATION`
19. `S6_SOURCES`
20. `S6_INTEGRATION_MAP`

### Underground_Cable_Thermal_Calculator_TRANSIENT_FINAL.xlsx — 22 sheets
1. `SESSION1_OVERVIEW`
2. `CAPABILITY_GAP`
3. `VERIFICATION_MATRIX`
4. `SCOPE_REGRESSION`
5. `ASTRA_REFERENCE_AUDIT`
6. `SOURCES`
7. `INVARIANT_TESTS`
8. `SESSION2_OVERVIEW`
9. `PARALLEL_SHARING_S2`
10. `METALLIC_LOSS_S2`
11. `S2_VERIFICATION`
12. `S2_INTEGRATION_MAP`
13. `S2_SOURCES`
14. `SESSION3_OVERVIEW`
15. `THERMAL_RC_INPUTS`
16. `CYCLIC_S3`
17. `EMERGENCY_CURVE_S3`
18. `S3_EMERG_SCAN_BACKEND`
19. `EMERGENCY_RATING_S3`
20. `S3_VERIFICATION`
21. `S3_SOURCES`
22. `S3_INTEGRATION_MAP`

## I. Unanswered/open questions needing an evidenced answer
1. Which actual cable manufacturer, part number, published construction, conductor/cable voltage class and installation guide apply to each real circuit?
2. Are the listed source records complete, licensed for public distribution, current and duplicate-free against original manufacturer evidence?
3. Which cables are physically single-core, three-core, sector/segmental, screened/armoured or have different conductor load distributions?
4. Which screen/armour/bonding construction and independent sheath/circulation loss method is correct for the real installation?
5. Are actual parallel cable sets electrically balanced or is a verified worst-set/individual-load allocation needed?
6. What are the exact installation routes, depths, spacing/formation, ducts, banks, spare ducts, concrete/backfill structures and physical thermal interfaces?
7. For air-filled conduit and HDD/casings, are measured or engineering-approved gap/air coefficients and complete T4 networks available?
8. Which measured soil moisture/resistivity, dry-out and seasonal earth-temperature conditions govern each section?
9. What are the true normal, peak, emergency, cyclic and harmonic loading and permissible conductor temperatures for every cable?
10. What temperatures or other field data are independently available to calibrate/validate the model and thermal capacitances?
11. Can every source-workbook formula block be tied to a published equation and validated actual site/software result, not merely a searchable Excel formula?
12. Which independent IEC, manufacturer, FEM or measured benchmarks substantiate multicore, bank, HDD, dry-out, cyclic, T1/T2/T3/T4 and full Neher–McGrath applicability?
13. Are the specific NEC/utility/owner requirements and conductor/code ampacity correction factors defined for each project?
14. Has the complete original React/Next/Vinext app successfully built, deployed and passed its own live-browser parity and PDF acceptance checks?
15. What are the formally acceptable release tolerances, qualified engineering review criteria, owner signoff and construction-stage hold points?
16. Can the deployed site legally publish all raw manufacturer/research tables from the 93-sheet workbook?
17. Have all study-case backups stored only in past visitors’ browsers been exported? Those records are not contained in the source archives.
18. Are there user-shared inline-only images or attachments in older private chats that are absent from the recovered export and current file list?

## J. Information/documents required to answer the open questions
1. Actual circuit schedule/one-line/load list (three-phase versus single-phase/DC, nominal voltage, frequency, AC load, power factor where needed, normal/emergency cycles and parallel set currents).
2. OEM cable drawings/datasheets and test reports: exact size/material/strand shape, diameter layers, conductor R20/α, skin/proximity parameters, shields/screens and armour, capacitance/dielectric loss, temperature ratings.
3. Route plans, trench/bank sections and coordinate table with phase/set layout, true center depths, XY offsets, physical clearances, crossings, HDD bore/casing/conduit geometry and lengths.
4. Measured native/backfill/concrete/duct-fill thermal resistivities and earth temperatures (including moisture, seasonal range, sensitivity and potential dryout).
5. Bonding/grounding arrangements and sheath circulating/eddy loss studies, screened metal materials and electrical continuity; verification of current sharing.
6. Air-gap and conduit model coefficients/duct wall material and temperature/source validity; independently verified complete equivalent T4 for supported specials.
7. Harmonic current spectrum and measured/verified frequency-dependent AC/screen/sheath resistances.
8. Thermal capacitance/heat capacity of cable components and soil, time-history or duty profile, thermal initial state and emergency temperature constraints.
9. Applicable standard editions, project/AHJ/utility/owner acceptance criteria, manufacturer installation limits, NEC ampacity tables/correction factors.
10. External validated numerical cases (IEC, manufacturer data, recognized software/FEM or paired measured temperature data) and convergence/uncertainty tolerances.
11. Engineer-of-record/owner confirmation for construction use and report approval matrix.
12. Authenticated live-original source build-and-browser evidence; audit of actual browser-local cases and complete file/source release manifests.
13. Standalone historical user PDFs/photographs if any were shared outside the source ZIP and are not currently recoverable.

## K. Engineering studies supported or possible with these source data
1. Steady-state buried-cable continuous ampacity and temperature screening (IEC 60287-oriented).
2. Conductor Rdc/Rac and temperature-feedback/skin/proximity-factor analysis.
3. Dielectric, screen/sheath circulation and armour loss contribution analysis.
4. Single-point, both-end and cross-bonding loss comparison where sufficient data exist.
5. Single-core trefoil, flat, horizontal/vertical and custom-layout comparison.
6. Multiple parallel sets and worst-set current-sharing assessment.
7. Mutual heating, soil-image coupling and unequal adjacent-circuit current analysis.
8. Heterogeneous cable constructions and mixed circuit thermal-network rating.
9. Balanced multicore supplied-network conductor-temperature screening.
10. Solid-filled conduit thermal path and T4 sensitivity.
11. Air-filled duct/conduit and gap heat transfer screening with verified coefficients.
12. Concrete duct-bank/group layout, position and occupancy comparative screening.
13. Trench, backfill layer and alternative soil thermal-resistivity sensitivity.
14. HDD/casing and crossing thermal penalty or verified T4 route bottleneck assessment.
15. Segment-by-segment route ampacity and worst thermal section selection.
16. Soil dryout, wet/dry-zone thermal threshold and field screening.
17. 2-D buried-cable/duct-bank finite-difference thermal-field mapping.
18. Mesh/domain/timestep sensitivity and energy-balance/convergence assessments.
19. IEC 60853-oriented hourly cyclic-load and periodic thermal response screening.
20. Short-duration and extended emergency cable temperature screening.
21. Emergency time/ampacity rating scans with exact duration and stable starting-state checks.
22. 24-hour load shape and load factor / thermal memory comparisons.
23. Soil rho, ambient, depth, group, current and conductor limit single-parameter sensitivity.
24. Environmental and loading robust/worst-case envelope studies.
25. Inverse design: maximum soil thermal resistivity at fixed load/margin.
26. Inverse design: minimum acceptable spacing and source-based trench layout.
27. Cable selection/ranking and parallel-set feasibility optimization.
28. Duct position optimization under candidate thermal loads.
29. Harmonic-current equivalent conductor heat and relative ampacity impact.
30. Manufacturer ampacity comparison under matched installation conditions.
31. NEC/code table ampacity factor and thermal-versus-code limit comparison.
32. Field measurement agreement, MAE/RMSE/max error and temperature residual analysis.
33. Uncertainty/conservatism parameter scan and validation evidence matrix.
34. Source-record completeness, missing-parameter and provenance quality assessment.
35. Cross-checking historical Excel workbook formulas/outputs against deployed code.
36. Exportable engineering input/assumption/report/JSON/CSV/XLSX/PDF source studies.

## L. Engineering boundaries
- Database rows or archived demo outputs are not project-specific physical evidence.
- Catalog presence does not prove source completeness, current OEM approval, numerical formula equivalence or code compliance.
- Screening tools do not automatically implement/certify complete Neher–McGrath, IEC 60287/60853, arbitrary FEM duct-bank/HDD, or construction-stage release without manufacturer-specific and measured inputs.
- Legacy private v3.6.2 React source has not been evidenced as compiled and anonymously deployed as the public application. The public site is a separate static implementation with recovered source modules.
- Previous inline-only images cannot be conclusively enumerated if they are unavailable from accessible conversation records; this register inventories all identifiable project images and PDFs in the supplied ZIP and relevant Library records.

## M. Cross-check summary
| Item | Pass 1 | Pass 2 | Pass 3 | Result |
|---|---|---|---|---|
| Design requirements | Recovered user chat | `FINALIZED_SCOPE.md` | Current project release register | Consolidated by subject |
| Master worksheets | Original workbook XML: 93 | Public manifest: 93 | Hosted `data/*.json` referenced files: 93 | Exact name/order/path PASS |
| Master data | Original workbook SHA-256 | Public manifest SHA-256 | Protected release handover checksum | PASS |
| Companion source | Private source archive 6 workbooks | Workbook sheets: 125 | `WORKBOOK_FEATURE_RELEASE.md` source map | Six categories consistent |
| PDFs | Original ZIP extensions: 4 | Exact file paths and archive bytes | Source design/QA folder identity | 4 complete names listed |
| Raster images | Original ZIP extensions: 9 | Exact file paths | Design/QA grouping and Library extra list | 9 complete names listed |
| User-specific physical construction values | No independent site drawing or OEM file in transferred ZIP | Reference record self-labelled demo | Provenance/release notes corroborate | Actual project values are not certified |

**Memory correction source:** Use this document and the original user files as the canonical project audit register. An audit file is not a direct edit to ChatGPT’s separate Memory summary. Full Memory summary review/change is available in Settings → Personalization → Memory summary → Manage.

## N. Exact field keys from recovered original source (machine-checked)
These lists are copied from executing `newStudy()` and `defaultField()` against the original source. They are intended to prevent a field from being forgotten when integrating or auditing the public UI.

### Root study object — 14 properties
`schema_version`, `project`, `name`, `notes`, `cable_id`, `cable_label`, `cable_source`, `voltage_rating_v`, `reference_example`, `units`, `controls`, `advanced_results`, `input`, `settings`

### Continuous model — 14 properties
`load_a`, `ambient_c`, `max_temp_c`, `soil_rho_km_w`, `burial_depth_m`, `cable_od_m`, `r20_ohm_m`, `alpha_per_c`, `ac_factor`, `dielectric_w_m`, `r_internal_km_w`, `r_dielectric_internal_km_w`, `group_multiplier`, `phases`

### Physical/electrical settings — 55 properties
`thermal_model`, `ac_model`, `dielectric_model`, `sheath_model`, `conductor_diameter_m`, `insulation_od_m`, `sheath_mean_diameter_m`, `enclosing_cores`, `insulation_rho`, `jacket_rho`, `ks`, `kp`, `epsr`, `tan_delta`, `capacitance_nf_km`, `screen_alpha`, `rating_mode`, `system`, `voltage_v`, `frequency_hz`, `installation`, `arrangement`, `group_mode`, `phase_spacing_m`, `parallel_sets`, `sharing_mode`, `sharing_source`, `worst_set_factor`, `set_currents_a`, `bonding`, `screen_r20_ohm_km`, `lambda1`, `lambda2`, `loss_source`, `armour_model`, `t1_km_w`, `t2_km_w`, `t3_km_w`, `dielectric_internal_km_w`, `verified_t4_km_w`, `t4_source`, `t4_validity_basis`, `equivalent_network_verified`, `equivalent_network_source`, `duct_id_m`, `duct_od_m`, `wall_rho`, `fill_rho`, `cable_basis`, `environment_basis`, `method_basis`, `cable_verified`, `environment_verified`, `method_verified`, `circuits`

### Circuit coordinate row — 5 properties
`name`, `x_m`, `depth_m`, `load_a`, `active`

### 2-D field options — 15 properties
`width_m`, `depth_m`, `nodes_x`, `nodes_y`, `ambient_c`, `omega`, `iterations_per_pass`, `convergence_tol_c`, `native_rho_km_w`, `dry_rho_km_w`, `dry_threshold_c`, `dryout_on`, `max_dry_passes`, `zones`, `sources`

### 2-D field zone row — 9 properties
`zone_id`, `active`, `kind`, `xmin_m`, `xmax_m`, `ymin_m`, `ymax_m`, `moist_rho_km_w`, `dry_eligible`

### 2-D field heat-source row — 6 properties
`source_id`, `active`, `x_m`, `y_m`, `heat_w_m`, `kind`

### Per-module controls (13 groups)
- **sensitivity (2):** `variable`, `values`
- **inverse (6):** `minimum_rho`, `maximum_rho`, `margin_c`, `minimum_spacing_m`, `maximum_spacing_m`, `step_m`
- **transient (18):** `profile`, `days`, `current`, `duration`, `increment`, `source`, `emergency_limit_c`, `conductor_area_mm2`, `conductor_diameter_mm`, `insulation_outer_diameter_mm`, `conductor_vol_heat_mj_m3k`, `insulation_vol_heat_mj_m3k`, `shell_vol_heat_mj_m3k`, `soil_vol_heat_mj_m3k`, `soil_mass_participation`, `timestep_min`, `gs_iterations`, `overrides`
- **field (0):** no persisted value; source default generated at runtime
- **networks (17):** `rows`, `ambient_c`, `soil_rho_km_w`, `rating_mode`, `source`, `verified`, `bank_enabled`, `bank_width_m`, `bank_height_m`, `bank_depth_m`, `bank_x_m`, `bank_rho_km_w`, `bank_source`, `dryout_on`, `dry_rho_km_w`, `dry_critical_rise_c`, `dry_source`
- **route (2):** `segments`, `advanced`
- **optimizer (11):** `rhos`, `ambients`, `depths`, `groups`, `loads`, `margin`, `ductSpacing`, `ductDepth`, `ductCount`, `ductMin`, `duct_layout`
- **scenarios (2):** `rows`, `advanced`
- **harmonics (2):** `rows`, `verified`
- **benchmark (12):** `manufacturer`, `source`, `cable_id`, `published_a`, `ambient_c`, `max_temp_c`, `soil_rho_km_w`, `burial_depth_m`, `installation`, `group_multiplier`, `conditions_verified`, `tolerance_pct`
- **candidates (10):** `candidate_ids`, `total_current_a`, `max_sets`, `circuit_spacing_m`, `burial_depth_m`, `phase_spacing_factor`, `margin_c`, `worst_set_factor`, `sharing_source`, `use_current_case`
- **code_comparison (17):** `code_name`, `edition`, `table`, `row`, `listing`, `source`, `cable_id`, `installation`, `conductor_limit_c`, `base_ampacity_a`, `ambient_factor`, `grouping_factor`, `installation_factor`, `other_factor`, `conditions`, `factor_source`, `conditions_verified`
- **field_validation (5):** `source`, `sensor_basis`, `verified`, `tolerance_c`, `rows`


---

## Cross-check conclusion and preservation rules

- All 39 written requirements are retained in Section A, classified as instructions rather than assumed site-measurement values.
- All 13 separately identifiable original input-transfer files (including embedded/historical workbook references) are listed in Section B, with provenance distinctions.
- Every archived source PDF (4), raster screenshot/design image (9), and SVG asset (5) is named in Sections E–F. Four separately identifiable Library JPGs are included with their generated provenance, plus two historical preview references explicitly flagged as uncertain.
- Every Master Database worksheet (93) and all six companion workbook sheet names (125 in total) are listed in Sections G–H.
- All 18 open questions, all 13 wanted-information items, and all 36 possible engineering studies are enumerated in Sections I–K.
- The original input object and all exact supported field keys appear in Section N, separately from actual site-supplied values.
- This is a cross-checked **reference register**, not a silent rewrite of independent ChatGPT Memory. For changes to your account's Memory summary, use **Settings → Personalization → Memory summary → Manage**; this report is the verified source document to use for those corrections.

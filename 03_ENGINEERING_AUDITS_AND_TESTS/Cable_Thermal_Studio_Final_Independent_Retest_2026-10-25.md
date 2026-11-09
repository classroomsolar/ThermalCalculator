# Cable Thermal Studio — Independent Rerun of Protected Public Baseline

**Baseline:** Current public website at https://headless-vmwfmgemqxl-classroomsolar-140e.wix-site-host.com/ (site ID 9ae05e15-0791-4a48-9bd3-5e90ae03a68e). No live release modification.

**Source compilation check:** Original React/Next/Vinext source `/mnt/data/r33_original` passed all ten offline checkpoints. This is **not** a successful React/Next/Vinext production build: required dependencies are not installed, and production build/browser cutover remain unverified.

**Public catalogue Excel regression:** `python qa_r42_catalog_regressions.py`: 24/24 test assertion groups PASS. All 93 workbook sheets and 256,429 source rows loaded. The existing public XLSX import/export and narrow-screen layouts passed local Chromium tests.

**Unified workspace regression:** `python r42_workspace_regressions.py`: PASS at seven responsive viewport widths, checksum tamper rejection, backup/restore, ID collision, idempotent restore, simulated storage-quota rollback and globally synchronized units. Browser tests run in the local asset harness rather than a remote HTTP browser.

**Persistence and import regression:** An initial test asserted before the file-input asynchronous import completed, although the import later succeeded. A corrected test copy, `qa_r42_persistence_fixed.py`, explicitly waits for the newly imported `external-unverified` case to become persistent before asserting its `verified:false` and `advanced:{}` markers. Rerun result: **11/11 PASS, zero page errors**. The application source was **not changed** by this test correction.

**Engineering limitation:** Passing the available source and browser regressions does not establish third-party engineering certification for all installation geometries or full original-React feature parity. A separate original production build and independently approved physical parameter sources are required for those distinct claims.

**Release decision:** Existing public Wix site protected; do not replace it with unbuilt original React source. Do not claim 100% feature parity or engineering certification. This document records measured test outcomes only.

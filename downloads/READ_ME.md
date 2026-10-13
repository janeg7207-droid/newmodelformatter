# NewModelFormatter 0.14 experimental

[Download the installer ZIP](NewModelFormatter_0.14_patch_installer.zip).

1. Extract into a **new empty folder**.
2. Run **Install.cmd** and select your **original Gorilla Model Formatter 1.0 EXE**.
3. Open **NewModelFormatter.exe** and convert the complete wrestler folder into a **new empty output folder**.
4. Rebake the complete output with **CakeView**, then open the conversion report.

The original EXE and input files stay preserved. No Python or Blender is needed.
Gorilla's UI, CakeView gate, folder input/output and YCL translator are retained.

0.14 includes:

- Requested ordinary-eye values: darkness **1.00**, falloff **0.50**, with other supported settings and texture references preserved.
- Guarded Cena-corresponding ocular anchors for the exact supplied Bryan/Flip profiles when their paired eye materials validate.
- A complete-mip DDS header correction, unique ring/entrance mesh verification, and verified original-writer weight normalization.
- An exact-profile Moxley WDF layout repair that preserves authored records and all original model/mask data.
- Read-only physics binding checks and durable final/error reports.

**Remaining limits:** Moxley's four YWA files still have mismatched source mesh references and remain omitted. Billie's WDF/YWA companions remain unsupported. Missing/unreadable masks, rejected textures and incomplete materials remain report problems. Teeth, eyes, beards, clipping, belt/blood and movement still need in-game checks; no universal visual fix is claimed.

**Validation:** 424 tests pass, including the extracted source ZIP. Seven exact-candidate Wine/native DLL checks passed; saved reports match the returned results. Installer bytes reconstruct the tested EXE exactly and ZIP CRCs pass. The Windows PowerShell installer and in-game appearance were not executed here.

[Detailed implementation and tested scope](NEW_FORMATTER.md).
[Source ZIP](NewModelFormatter_0.14_source_patch.zip).
[Validation](NewModelFormatter_0.14_Package_Validation.json).
[Exact remaining inputs](FILES_NEEDED.md).

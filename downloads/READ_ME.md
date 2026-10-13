# NewModelFormatter 0.14.1 experimental

[Download the installer ZIP](NewModelFormatter_0.14.1_patch_installer.zip).

1. Extract into a **new empty folder**.
2. Run **Install.cmd** and select your **original Gorilla Model Formatter 1.0 EXE**.
3. Open **NewModelFormatter.exe** and convert the complete wrestler folder into a **new empty output folder**.
4. Rebake the complete output with **CakeView**, then open the conversion report.

Original files, Gorilla's UI, CakeView gate, folder input/output and YCL translator are preserved. No Python or Blender is needed.

0.14.1 fixes:

- Material checks now use Gorilla's innermost `Characters` folder when output paths contain two such folders. This lets valid paired eye materials pass the supported Bryan/Flip ocular checks; wrong bindings still fail.
- A plain unknown `.ywa` companion triggers checked translation of its readable paired YCL. The unknown blob stays omitted and conversion stays incomplete. No physics is invented.
- Rejected animation-core reasons appear in each model's problems as well as the overall report.

The existing 0.14 eye defaults remain **darkness 1.00 / falloff 0.50**. Exact-profile ocular, DDS, mask and Moxley WDF repairs remain guarded.

**Latest report:** 57 of 79 model checks passed. The 22 failures comprise 16 unreadable masks, five missing source animation roots and Santino's unidentified body mesh. Passing model checks do not establish complete materials, physics or game readiness. [Full compact review](Uploaded_Batch_Report_Review_0.14.1.json).

**Limits:** Moxley's four YWA bindings, Billie's WDF/YWA companions and unknown plain YWA remain unsupported. Jeff's actual Hat/Ponytail YCL and Matt's failed YCL sources are unavailable. Missing/rejected textures, materials and unreadable masks stay problems. Teeth, eyes, beards, clipping, belt/blood and movement still need in-game checks.

**Validation:** 441 tests pass from the source ZIP. Exact final payload checks under Wine/native DLLs passed for Bryan's nested legacy conversion, existing 2K26 repair and repeat run; two controlled YWA cases; Moxley's WDF structure; and the UI. Source/input hashes and saved reports were checked. Installer bytes reconstruct the tested EXE exactly; ZIP CRCs pass. Windows PowerShell installation and in-game appearance were not tested here.

[Detailed implementation and tested scope](NEW_FORMATTER.md).
[Source ZIP](NewModelFormatter_0.14.1_source_patch.zip).
[Validation](NewModelFormatter_0.14.1_Package_Validation.json).
[Remaining inputs for earlier unresolved cases](FILES_NEEDED.md).

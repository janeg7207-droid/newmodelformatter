# NewModelFormatter 0.14.2 experimental

[Download the installer ZIP](NewModelFormatter_0.14.2_patch_installer.zip).

1. Extract into a **new empty folder**.
2. Run **Install.cmd** and select your **original Gorilla Model Formatter 1.0 EXE**.
3. Open **NewModelFormatter.exe**. Leave **Body-atlas teeth/mouthbag: use skin shader** selected. Convert the complete wrestler folder into a **new empty output folder**. For existing 2K26 files, choose **Keep the mod's own folder name**.
4. Rebake the complete output with **CakeView**, then open the conversion report.

Original files, Gorilla's UI, CakeView gate, folder input/output and YCL translator are preserved. No Python or Blender is needed.

0.14.2 teeth rule:

- Eligible teeth and mouthbag materials using verified local body textures are recreated as native **yCh_skin / 0x19**, matching the supplied working Gorilla 2K24 report and manual CakeView method.
- Both materials use their existing `body_color` and `body_nrm` references. No alpha inversion, texture repainting, geometry or vertex-mask edits are added.
- Existing native material-link recovery runs first. The shader step preserves those links. Extra authored maps, incorrect bindings and unknown or invalid schemas remain refused.
- Already eligible skin materials are left unchanged. The rule is selected by default in this app and can be disabled.

The exact supplied BigBoomAJ native model can receive a material-only repair despite its missing unrelated body/eye/head JMTLs. Those failures and its incomplete status remain reported; no unrelated material is invented. Use the complete wrestler folder when converting and baking.

Existing 0.14.1 changes remain:

- Material checks now use Gorilla's innermost `Characters` folder when output paths contain two such folders. This lets valid paired eye materials pass the supported Bryan/Flip ocular checks; wrong bindings still fail.
- A plain unknown `.ywa` companion triggers checked translation of its readable paired YCL. The unknown blob stays omitted and conversion stays incomplete. No physics is invented.
- Rejected animation-core reasons appear in each model's problems as well as the overall report.

The existing 0.14 eye defaults remain **darkness 1.00 / falloff 0.50**. Exact-profile ocular, DDS, mask and Moxley WDF repairs remain guarded.

**Earlier bulk report:** 57 of 79 model checks passed. The 22 failures comprise 16 unreadable masks, five missing source animation roots and Santino's unidentified body mesh. Passing model checks do not establish complete materials, physics or game readiness. [Full compact review](Uploaded_Batch_Report_Review_0.14.1.json).

**Limits:** Moxley's four YWA bindings, Billie's WDF/YWA companions and unknown plain YWA remain unsupported. Jeff's actual Hat/Ponytail YCL and Matt's failed YCL sources are unavailable. Missing/rejected textures, materials and unreadable masks stay problems. Teeth, eyes, beards, clipping, belt/blood and movement still need in-game checks.

**Validation:** 469 tests pass from the source ZIP. Exact final payload checks under Wine/native DLLs passed for the supplied BigBoomAJ files with the rule off/on and a repeat run; the complete Bryan 2K25 folder off/on; and the UI. Only the two JMTLs changed between off/on; repeat conversion changed no assets. Original/input hashes and saved reports were checked. Source rebuilding and installer reconstruction produce the tested EXE exactly; ZIP CRCs pass. Windows PowerShell installation and in-game appearance were not tested here.

[Detailed implementation and tested scope](NEW_FORMATTER.md).
[Source ZIP](NewModelFormatter_0.14.2_source_patch.zip).
[Validation](NewModelFormatter_0.14.2_Package_Validation.json).
[Working 2K24 teeth reference](Working_2K24_Teeth_Reference_0.14.2.json).
[Mixed 2K22–2K25 target for 0.16–0.17](ROADMAP.md).
[Remaining inputs for earlier unresolved cases](FILES_NEEDED.md).

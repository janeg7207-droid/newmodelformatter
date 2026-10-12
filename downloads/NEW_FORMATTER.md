# NewModelFormatter 0.6 experimental — independent Gorilla YCL translation

Version 0.6 fixes the folder rule that skipped readable YCL files whenever
WDF/YWA companions were present. It keeps Gorilla's actual YCL translator
unchanged. Source files, CakeView, folder input/output, stock-slot mapping and
Gorilla-style UI remain. Convert into a new empty output folder.

## Install and use

1. Extract `NewModelFormatter_0.6_patch_installer.zip` into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`. Use your existing CakeView and
   convert the original Billie folder again into a new empty output folder.

No YCL checkbox or new input method is needed. The output should contain
`873_Default_Attire/873_Attire.ycl`; the JSON report records it in
`physics_converted` with `original_gorilla_translator: true` and header version 26.
The patch identifier is `material-mask-native26-reference-ycl-6`.

The installer creates a separate EXE and refuses to overwrite an existing
output. Do not select the older experimental EXE as installer input. No Python
or Blender installation is needed to run this repair tool.

## YCL evidence and limits

59 regression tests passed under Python 3.14, including original Gorilla YCL
bytecode fixtures, failure preservation, companion omission, source/output
separation and stock-slot exclusions. An isolated folder conversion of the
actual supplied Billie MCD, MTLS, HPL, YCL and all five companions ran under
Wine. Model verification passed, the 13 nonsimulation materials were emitted,
and source files stayed unchanged. The output YCL is 1,254,192 bytes, version
26, with the original joint/mesh names. SHA-256:
`b3560ad5cb4450e2fdc54f2c01ff6befcff2679e4ba211f88e646197ea4e2ec9`.
It matches the earlier reference-validated output. A fresh independent
YclEditor read/write under Wine also produced byte-identical 2K26 output.

The runtime wrapper checks version, header size, source/target names and root
tree parsing before committing output. It does not require an external editor;
the independent editor round-trip was a separate packaging test. UI startup
passed under Wine/Xvfb with CakeView still required and the gear option off.
The Windows PowerShell installer and in-game motion have not independently
been tested here. These isolated Billie checks lacked her paired base model.

**YCL format translation does not complete Billie's physics conversion.** Her
YCL also contains outfit references absent from the supplied attire. The five
WDF/YWA files remain omitted and the report stays incomplete. The supplied
PWM parser confirms WDF `M_Pierce` is absent from the model; hair corrective
data declares M_Hair 10,014 / S_Hair 1,059 vertices while the model has
6,719 / 363. Do not copy those 2K25 bytes into output as assumed compatible
2K26 physics. To continue collision rebinding, the exact original Billie
`873_Billie_Starkz/BaseModel/baseModel.mcd` is needed.

## Retained repairs

* Unique case reconciliation for Billie's `hair_ALPHA` / `hair_alpha` material
  binding; ambiguous collisions fail rather than choosing a definition.
* Guarded Rey mask recovery with his now-supplied original paired base:
  native verification passed, Body/Head remap/topology retained, every mask
  index valid, complete 490,532-byte HPL preserving ring/entrance arrays.
  The optional ancestor-remap gear profile remains off by default. Coverage
  and movement still need entrance/gameplay tests. No Rey physics is invented.
* Existing native 2K26 models are accepted in a preservation/material-audit
  path. Select **Keep the mod's own folder name**. Opaque JMTL texture hashes
  cannot safely be relocated to another stock slot. Models/material payloads
  and native companions are preserved; geometry and old physics are not rebuilt.
* Copied reference weight checks remain read-only report diagnostics. Valid
  numeric weights can still be anatomically wrong. No new teeth/blood/belt
  repair is claimed.

## Supplied reference source

All 100 supplied source/configuration files are preserved with hashes in
`reference_source/`. The newly supplied WWE2K_MDL includes import/export,
Heat Seek, hair alignment, HPL and physics code. Its VCModel.dll is identical
to Gorilla's bundled DLL. The missing-add-on source blocker is resolved.

The current shipped tool uses the original native engine plus tested repairs;
the full Blender scene workflow has not replaced that engine. The reference
physics embedder passes existing companion bytes through, and its remapping
paths need matched geometry/colliders. Source availability alone is not proof
of compatible physics. An optional surface-weight prototype failed a native
verification check and is retained outside this release, rather than shipped
as a validated gear repair. The supplied Blender YCL workflow is not substituted
for Gorilla's translator.

## New dark-eye report

The screenshot shows dark Billie eye surfaces. Her eye geometry/material
inputs have not yet been uploaded: available BaseModel files are Rey's.
Investigation requires Billie's original `BaseModel/baseModel.mcd`, original
`BaseModel/baseModel.mtls`, and converted `BaseModel/Materials/eye_l.jmtl`.
The reference includes texture-binding fixes, but none is enabled for her eyes
without inspecting those inputs. This build includes the YCL skip correction,
not a claimed dark-eye fix.

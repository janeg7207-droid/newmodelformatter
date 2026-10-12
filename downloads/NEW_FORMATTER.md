# NewModelFormatter 0.7 experimental

This build adds reliable final/error reports and an optional new Rey gear
weight test. Folder input/output, CakeView, the Gorilla-style UI and Gorilla's
YCL translator remain. Original files are preserved.

## Install

1. Extract `NewModelFormatter_0.7_patch_installer.zip` into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`. Convert into a new empty output
   folder using your usual CakeView workflow.

Select the original Gorilla EXE, not an older experimental EXE. No Python or
Blender is needed to run the tool. The installer refuses existing output files.

## Reports

After conversion, use **Open conversion report**. The log prints the saved path.
`<source folder> - conversion report.json` is saved at the selected output root
and inside the converted mod folder. Both copies include final model, material
and YCL results. Conversions with failed checks still produce a report. Fatal
errors produce a failure report retaining completed records when available.
Writes are atomic. If the output is unwritable, the tool uses
`%TEMP%\NewModelFormatter\Reports` and prints that path. If neither location is
writable, it prints the report-write error and preserves the conversion error.
The report button falls back to Notepad when JSON has no file association.
Forced process termination cannot guarantee a completed report.

## Rey test

For the supplied original 2K25 Rey folder, enable **Rey gear: match paired body
weights (experimental)**. This replaces the earlier ancestor-remap test. It
projects weights from the verified converted paired body onto tights, tops,
belt, shoulder pads and wings. The 1% cleanup and nearest-triangle math come
from the inspected reference source; native output has at most eight influences.
It is not claimed equivalent to the complete Blender Heat Seek workflow.

This profile accepts only the exact inspected attire/base pair. The base must
pass the original verifier. Every written gear influence is independently
checked against the requested projection, in addition to the original geometry,
rig, material-binding, flag and mask checks. No Rey physics is created.

Actual-file conversion under Wine passed base/attire verification. All 14
attire meshes retained positions, triangles, UVs, remaps and material bindings.
21,573 projected gear vertices passed written-weight checks, with maximum
error below 0.001961; normalized weights intentionally assigned to the wrong
bone were rejected on each of the five meshes. The guarded restored hide mask
still preserves ring/entrance data and all Body/Head indices are valid.
This establishes conversion behavior, not that the see-through issue is fixed
in game. Check boots/tights, belt, shoulders and wings during entrance/movement.

## Billie YCL and remaining limits

Readable YCL converts even with unsupported WDF/YWA companions. The original
Gorilla translator is unchanged. The supplied Billie conversion retained the
same verified YCL SHA-256 as 0.6:
`b3560ad5cb4450e2fdc54f2c01ff6befcff2679e4ba211f88e646197ea4e2ec9`.
Model checks passed and the material case mismatch remains repaired.

Her five WDF/YWA companions remain omitted: their mesh/vertex references do
not match the supplied attire, and her paired base is absent. YCL format
translation does not prove compatible cloth/hair movement. Reports remain
incomplete. No unchanged 2K25 companion is treated as compatible 2K26 physics.

Billie's dark eyes remain unresolved. The stock reference supplied is Cena's
native model/material table; it contains no actual eye shader payloads. Her
original `BaseModel/baseModel.mcd` and `baseModel.mtls` are still needed for
her eye/collider investigation. No eye, teeth or general blood/belt shader
repair is claimed.

The supplied AJ pair is native 2K26 with empty embedded hide masks. This build
adds a hash-guarded, automatic **foot-only mask test** for that exact pair.
Keep the normal wrestler folder structure with `BaseModel/baseModel.mcd` and
`610_Default_Attire/610_Attire.mcd`, and select **Keep the mod's own folder name**.
No separate HPL is needed. The 2,108 selected body indices have more than 50%
combined foot/toe influence and belong to the real paired-body remap domain.
Both ring/entrance flags are emitted at all five LODs. Only the exact empty-HPL
tail is replaced; the complete model payload, rig, shapes, weights and physics
are retained byte-for-byte. Existing nonempty/sidecar masks are preserved.
This repairs a specific missing foot-mask case; it is not a whole-outfit HPL
reconstruction. Native reader checks are required before committing output,
and boot coverage still needs an in-game check. The report records
`aj_foot_mask` and `repaired_2k26_foot_mask`.

AJ's beard remains unresolved. Its `M_Combinations` mesh binds to
`combinations_ALPHA`. The missing shader file is
`610_Default_Attire/Materials/combinations_ALPHA.jmtl`; the supplied base MTLS
contains reference stubs without beard shader parameters. No beard fix is
claimed until that actual material can be inspected.

## Existing 2K26 inputs and source

Existing 2K26 models are accepted for preservation/material audit. Select
**Keep the mod's own folder name**; moving opaque material texture hashes to
another stock slot is unsupported. This path preserves native model and
physics bytes, except for the explicitly reported exact-AJ foot-mask repair.
It does not rebuild unsupported old skinning/physics.

The source ZIP includes runtime repairs, build code, tests and all 100 supplied
source/configuration snapshots with hashes. The full Blender scene pipeline
has not replaced the original native engine. Original Gorilla EXE/mod assets
are excluded. See `SOURCE_REBUILD.md`.

89 regression tests passed under Python 3.14 with NumPy. Wine/Xvfb tests covered
Rey, Billie YCL/materials, existing 2K26 byte preservation, AJ foot-mask
embedding, fatal-error Temp reporting, and the GUI report button. Sources stayed unchanged, and root/mod report copies matched the final
returned reports. CakeView remained required. The PowerShell installer was
checked by exact binary reconstruction and ZIP CRCs; it was not independently
executed on Windows here. In-game appearance/movement tests remain required.

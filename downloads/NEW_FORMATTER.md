# NewModelFormatter 0.8 experimental

This build adds missing-data checks and supported recovery for already-ported
2K26 models, and admits actual 2K24 model files through the native reader.
It retains final/error reports and the optional Rey gear weight test.
Folder input/output, CakeView, the Gorilla-style UI and Gorilla's
YCL translator remain. Original files are preserved.

## Install

1. Extract `NewModelFormatter_0.8_patch_installer.zip` into a fresh folder.
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

Existing 2K26 models are accepted for preservation and missing-data checks. Select
**Keep the mod's own folder name**; moving opaque material texture hashes to
another stock slot is unsupported. The new pass checks material definitions,
texture references, hide masks against the actual paired base, and available
physics references. Its supported repairs are:

- Rebuild a missing native MTLS table or entry from actual readable JMTLs in
  the selected folder. Existing shader values are retained.
- Recover referenced DDS/TEX files when an exact game-path hash identifies
  an available source file. Missing hashes are reported as external or missing;
  stock game assets may resolve them at bake/runtime.
- Restore an empty, absent or unreadable embedded mask from a readable,
  matching HPL sidecar after paired-base/domain and native-reader checks.
  This supports uniform LOD masks and preserves the model and all other streams.
- Restore an available YCL using Gorilla's existing translator where supported.
  Existing native WDF/YWA companions remain preserved but unverified.

Inspect `native_2k26_missing_data_check` and each model's
`native_missing_data_audit` in the report. Unavailable shaders, textures,
paired bases, masks or physics remain listed with their expected paths/hashes.
The pass does not regenerate missing geometry or arbitrary outfit masks.
Unreadable/ambiguous layouts remain preserved and reported.

Actual native-file tests restored all 13 Billie material bindings after
deleting a table or entry in test copies. Healthy model/shader bytes stayed
identical. A deliberately removed Rey embedded mask was recovered from his
valid sidecar and exactly matched the earlier validated mask; all other model
substreams stayed identical. These isolated tests still lacked textures or
physics/material assets, so their reports correctly retained unresolved items.

## 2K24 inputs and Xia Li

Native model format 40 (0x28) now passes the folder admission gate. The backend
reads the original bytes as 2K24; no header is relabeled as 2K25. Original rig
and output checks remain active. Unsupported older rigs retain failures.
2K24 conversion is experimental: materials, masks, texture conventions and
physics require their own checks, followed by an in-game check.

The supplied original Bryan ROH base and attire are genuine format-40 inputs.
Both converted to format 47 with 209 -> 175 bones and passed native structural
checks. His original 67,580-byte HPL was readable, converted to a complete
168,932-byte embedded mask, and preserved flags/indices at all five output
LODs within the actual paired-base domains. His MTLS/material files were not
supplied with this pair, so these
checks do not establish a complete, bake-ready mod.

Xia Li's supplied base and attire are format 41 (2K25). Neither contains an
embedded HPL. Her report's separate 81,408-byte HPL is byte-identical to the
unreadable placeholder previously observed with Rey/Bryan. Her exact missing
mask source is a readable `982_Default_Attire/982_Attire.hpl` matched to the
supplied base. Another wrestler's mask cannot substitute for it. Xia's YCL
was translated in her report, but four YWA companion files were omitted;
compatible movement remains unverified.

The source ZIP includes runtime repairs, build code, tests and all 100 supplied
source/configuration snapshots with hashes. The full Blender scene pipeline
has not replaced the original native engine. Original Gorilla EXE/mod assets
are excluded. See `SOURCE_REBUILD.md`.

114 regression tests passed under Python 3.14 with NumPy. Wine/Xvfb tests covered
Rey, Billie YCL/materials, existing 2K26 byte preservation, AJ foot-mask
embedding, actual 2K24 conversion, native missing-data recovery, fatal-error
Temp reporting, and the GUI report button. Sources stayed unchanged, and root/mod report copies matched the final
returned reports. CakeView remained required. The PowerShell installer was
checked by exact binary reconstruction and ZIP CRCs; it was not independently
executed on Windows here. In-game appearance/movement tests remain required.

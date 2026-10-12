# NewModelFormatter 0.12 experimental

This build repairs named local texture bindings for supported legacy materials,
preserves explicitly authored teeth irradiance, and automatically restores the
original supplied Bryan mask for his exact inspected formatted-2K25 pair. This
covers supported inputs that previously passed through 2K24 -> 2K25 formatting.
Gorilla-style folder input/output, CakeView, YCL translation, the original UI
logic and original source files remain preserved. Appearance still requires
an in-game check; this is not a confirmed universal eyes/teeth/beard repair.

## Install

1. Extract `NewModelFormatter_0.12_patch_installer.zip` into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`. Convert into a new empty output
   folder using your usual CakeView workflow.

Select the original Gorilla EXE, not an older experimental EXE. No Python or
Blender is needed to run the tool. The installer refuses existing output files.

## New 0.12 checks

Older partial male rigs can pass the source-rig gate when their complete
animation core and stock bind pose are recognized. Gorilla already builds the
175-bone target rig; this extension preserves its bone builder, original
mapped weights and custom bones. Admission additionally verifies every written
bone name/order, parent, bind matrix and skin influence, including normalized
weights attached to the wrong bone. Missing animation joints, malformed rigs,
unrecognized poses and failed geometry checks stay unsupported. Inspect
`partial_legacy_rig`. A separately unreadable HPL still leaves the model check
failed; this is not a mask repair or a general body/cloth clipping guarantee.
No extra stock-body projection, new physics or altered input/output method is
introduced for this route. The actual supported sample and regression evidence
are recorded in the package validation. The actual sample 576 base (130 source
bones) and attire (97 source bones) each wrote 175 stock bones plus six custom
bones. The base now passes the original model verifier; the attire keeps its
unreadable-mask failure. Every skin weight was checked across 35,838 vertices.
Both MCDs are byte-identical to the prior 0.11 output, proving no additional
geometry, shape or weight changes from this admission extension.

Every recorded output, including preserved native 2K26 files and failed
conversion outputs, receives `face_output_audit`. `face_output_check` records
coverage and distinguishes face models, attire without face meshes and
unavailable outputs. It reads the actual model domains, UVs, vertex colors,
normals/tangents, material triangle ranges and shading-anchor references. It
then resolves MTLS path hashes to actual available JMTLs and texture paths.
Missing required local links are problems; unavailable external game assets
remain explicitly unverified. Eye colors may legitimately differ. Teeth using
custom atlases remain preserved; a comparison-style skin shader is supported
when its references match an inspected body atlas. No stock UVs, textures or
anatomical anchor positions are copied over custom models.

The earlier supplied native 2K26 Cena model is a schema reference, not a
replacement mesh. Its provenance appears in the report. The later
`139_John_Cena_2019.7z` upload exceeds the transfer limit and was not inspected.
The audit does not certify brightness, tooth appearance, baking or game lookup.

## Existing 0.11 repairs

The actual formatted-2K25 Bryan archive was supplied and converted with the
bundled native engine. Its body atlas contains tooth/gum pixels and its UV0
samples those islands correctly. Source/output teeth and eye geometry, remaps,
UVs and vertex colors remained identical. No UV swap or texture whitening is
justified by this data.

All named local eye/body/head/teeth/hair/gear texture references retained old
hashes that differ from the copied destination paths. The comparison formatter
binds the actual DDS files named by its source materials and then hashes their
destination `.tex` paths. 0.11 follows that local binding policy when a unique
valid named DDS exists in the matching source Textures directory. It copies
unchanged texture bytes and emits the actual destination reference. Global,
null and unavailable local references are retained. Ambiguous or invalid local
data produces explicit problems; no guessed substitute texture is made.
Inspect `local_texture_bindings` and its findings in each material report.
This proves emitted local bindings, not CakeView bake or in-game resolution.

Gorilla also overwrote Bryan's explicit source teeth irradiance RGB
`1.0 / 0.75 / 0.75` with `0.0 / 0.7490196 / 0.7490196`. 0.11 retains finite
explicit source components in the normalized 0..1 range for teeth/mouthbag.
Missing or unsupported values retain existing defaults. The shader and UVs
remain the original teeth conversion. This repairs source-value loss without
claiming that the black rendering cause has been established in game.

The earlier supplied readable Bryan HPL is valid for this exact archive pair:
native inspection proved original-v40 and formatted-v41 Body/Head positions,
triangles, remaps and UVs identical. Automatic restoration requires exact
source base/attire and invalid-sidecar fingerprints, successful converted-base
verification, unchanged remap topology and every mask ID in the real domain.
The report uses `supplied_hide_mask_recovery`. Valid sidecars, intentional empty
masks and readable embedded masks retain priority. No arbitrary mask is created.
All 4,215 original Body mask IDs are retained for ring/entrance at five output
LODs, including all 2,109 foot/toe-dominant IDs. Boot coverage still requires
an in-game movement check. This automatic profile does not apply to unrelated
Bryan models or Flip; Flip's intact original mask remains unavailable.

Named local hair/beard texture bindings are included in the repair when the
actual files exist. Shader variants, hair geometry and texture pixels are
preserved; speckled beard appearance has not been confirmed repaired.

Vynx's actual default Heat Seek uses Blender `DATA_TRANSFER` with
`POLYINTERP_NEAREST`, matching all bone groups, object transforms, <1% cleanup,
normalization and reparenting. The comparison formatter prepares a joined stock
Body+Head donor. The current paired-body Rey projection is a related native
policy, not the complete Blender workflow. For this Bryan archive the missing
mask was proven independently of the weights; his shoes originally remained
unreweighted while body weights changed. A general Heat Seek replacement is
not claimed or activated from those observations alone.

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

## Unsupported materials and Bryan's loading crash

The original material reader returns no parsed materials for every non-v3
inline block. Previously the caller interpreted that result as "already 2K26"
and copied the library unchanged. Only the exact native v6 library with empty
v4 stubs is now accepted as a native table. Unsupported, ambiguous or malformed
layouts remain explicit problems and are withheld from a fresh output; existing
output files and source files are never deleted. Material-row problems affect
the final conversion status. The usual input/output and CakeView flow remains.

Bryan's supplied 0.9 report converted genuine 2K24 models but skipped all four
material-library instances with the old "already 2K26" label. His reported
in-game loading crash has not been reproduced or attributed to a specific asset.
The format guard prevents this particular unsupported-material success path;
it does not establish a crash repair. His original `BaseModel/baseModel.mtls`
(8,640 bytes) and `159_Default_Attire/159_Attire.mtls` (9,800 bytes) are still
needed to inspect the actual blocks and implement a tested older-material adapter.
The original models and readable HPL have already been supplied.

A later multi-mod 0.9 INPUT report is a different case: all 12 models are
format 41 inputs and all 12 material libraries converted, producing 102 payload
audits. It has four unreadable-mask failures plus Xia's unsupported physics
companions. It does not reproduce the earlier raw-2K24 material-skip path.

## Flip Gordon and future hide-mask failures

Flip's supplied 0.9 report identifies the same 81,408-byte HPL seen in earlier
Rey/Xia ports: SHA-256
`57abd17dd82782bcd4c1509c311d3f70227af707e7975a2e1b3fcbf1eae2c3dd`.
The available identical bytes contain invalid record framing and indices far
outside his reported body domain. This is not a usable outfit mask, and changing
its mesh name does not restore the data.

The legacy fallback uses only a readable, nonempty HPL already inside the
selected source attire. It requires a successfully verified converted paired
base, unchanged Body/Head remap topology, and every mask index in the actual
domain. Valid sidecars and the existing exact-Rey recovery keep their priority.
No body coverage is inferred from gear names and no mask from another wrestler
is substituted. If no usable mask exists, the conversion remains incomplete.

Flip's actual `_formatted_2K25` source base/attire were subsequently supplied.
Their SHA-256/size match the report and the native reader sees format 41 with
no recoverable embedded HPL. His uploaded converted format-47 files contain
only empty 12-byte masks. The supported fallback therefore cannot recover his
outfit coverage from these files. The remaining required mask source is a
readable `931_Default_Attire/931_Attire.hpl` from the original mod archive,
before `_formatted_2K25`. Another copy of the known invalid HPL will not help.
Any recovered mask still needs entrance/gameplay coverage checks.

## Eye/teeth checks and Ricochet jacket investigation

Each freshly converted material library now records
`written_material_payload_audit` from its actual JMTL bytes: SHA-256, shader and
texture hashes. Eye/teeth entries include `face_texture_check`. Native-input
material audits include the same checks. The expected teeth pair is
`0x7357EEB9075DF170` / `0xBA65216DD64F5C78`; the expected eye normal is
`0xEFBC052176B84E95`. Captured 2K26 character material observations inside the
supplied comparison formatter corroborate these reference values.

Default emitted teeth hashes matched this pair in the exact packaged writer.
Caller-supplied teeth references remain preserved and are distinguished from
the reference pair. Left/right eye test materials retained the requested color
and emitted the expected normal. The available converted Bryan/Xia and supplied
native reference models had 13 valid shading-anchor mesh/vertex references and
the expected eye bindings/bones. These checks do not establish anatomical
anchor placement, game lookup of textures, or the affected screenshots' output.
Earlier 0.8 reports have shader/type metadata without actual texture hashes.
The later multi-mod 0.9 report records matching left/right eye hashes and the
expected normal reference on every base. Five of its six teeth/mouthbag pairs
match the corresponding body color/normal references; HBK has the shared teeth
color with a custom normal reference. This establishes reported bindings,
not actual DDS resolution or correct sampling. Black teeth and dark eyes remain
unresolved pending affected material/texture pixels and game checks.

The available converted teeth models have two UV channels versus one in the
stock reference, with different layouts. Comparing raw triangle order between
different models provides no corresponding-triangle evidence for a channel
swap. The comparison formatter's active C# material pass binds body atlas
textures to teeth, whereas the Python writer defaults to shared stock teeth
textures. An atlas layout may therefore be intentional. Actual affected DDS
pixels and material references are needed before selecting a texture or UV
repair. UVs and vertex colors remain unchanged.

The supplied comparison archive contains stored material observations, not the
original stock teeth JMTL or DDS pixels. No texture is fabricated or generic
teeth material substituted over custom data. See FACE_RENDERING_INVESTIGATION.md.

Gorilla treated every DXT1 texture as opaque. DXT1 can contain transparent
pixels when the BC1 palette has three colors and a used pixel selects entry 3.
The correction checks those actual selectors, ignores padding outside the
image, and handles BC1 in DX10 headers. Truncated/unsupported layouts remain
unknown; other formats retain Gorilla's decoder. Texture bytes are unchanged.
The existing material conversion policy uses this corrected classification.
Existing native JMTL variants are preserved rather than guessed/replaced.

Ricochet's report lists `jacket` and `jacket_trans` as yCh_trans inputs, with no
explicit output transparency variant, and an unreadable hide mask. This is
not enough to establish the cause of the angular patches in his screenshot.
His `1029_Default_Attire/1029_Attire.mcd`, `.mtls`, `Materials/jacket.jmtl`,
`Materials/jacket_trans.jmtl` and referenced DDS files are needed for that
specific material/geometry comparison. A ZIP of the affected wrestler folder
preserves the files/structure. No Ricochet visual fix is claimed.

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

Adam Cole's uploaded `combinations_ALPHA.jmtl` is a valid 312-byte shader-0x16
material with explicit short-hair length 2. Its flow/combo hashes are
`0x598227A899698A95` and `0xBE61F330147146CD`. The pixel-mask slot is explicitly
unbound, which does not prove a missing required texture. This file alone does
not explain the speckling. His matching output `880_Attire.mcd` and associated
`Textures` folder are needed for mesh bindings, UVs and actual texture channels.

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

168 regression tests passed under Python 3.14 with NumPy. Earlier Wine/Xvfb
checks covered
Rey, Billie YCL/materials, existing 2K26 byte preservation, AJ foot-mask
embedding, actual 2K24 conversion, native missing-data recovery, fatal-error
Temp reporting, and the GUI report button. New exact-build checks covered the
emitted eye/teeth references, native eye/teeth data inspection, BC1 classification,
Billie material/YCL output and UI. Sources stayed unchanged, and root/mod report copies matched the final
returned reports. CakeView remained required. The PowerShell installer was
checked by exact binary reconstruction and ZIP CRCs; it was not independently
executed on Windows here. In-game appearance/movement tests remain required.

Exact 0.10 Wine checks recovered the existing supplied Bryan HPL from a
controlled legacy MCD fixture built with his actual original model payloads.
An invalid sidecar did not suppress that intact mask: original flags/indices
were preserved at all five output LODs and validated against the converted
paired base. An independently constructed unsupported-v2 material table was
withheld and its error reached both final report copies. This specimen is not
Bryan's unavailable actual MTLS. Actual Flip original files reproduced the
known-invalid-mask diagnosis without claiming a recovery, and his already
converted files stayed byte-identical. Rey's original recovery/gear checks,
Billie's YCL/material output, representative face/BC1 checks and the UI passed.
Original uploads and isolated source copies remained unchanged.

## 0.11 validation and remaining scope

196 regression tests passed. Exact 0.11 Wine conversion of the untouched
uploaded Bryan archive passed both native model verifiers. All 26 named local
texture bindings matched actual copied destination paths; all 23 DDS files
were byte-identical. Both eye materials bound the supplied eye color and kept
the reference global normal. Teeth/mouthbag JMTLs exactly matched the supplied
reference writer with the original RGB irradiance (serialized 255/191/191),
using the matching body atlas color and normal paths. Eye/teeth/mouthbag
positions, triangles, remaps, UVs and colors remained equal to the source.
Automatic supplied-mask recovery retained all flags and 4,215 Body indices at
five LODs, masking all 2,109 foot/toe-dominant indices. Both final report copies
matched the returned result. The only Bryan report problem is the explicit
requirement to check restored-mask coverage in game; both model checks passed.

Original Rey mask/gear behavior, Billie material/YCL behavior, unsupported
material withholding, embedded-mask recovery, native Flip preservation and
the CakeView-gated UI passed their native regression checks. The exact final
EXE matches the tested candidate; binary reconstruction and ZIP integrity are
checked. Windows PowerShell installation and in-game appearance remain unrun.

This repair covers supported named local texture/lighting loss in formatted
2K25 inputs, including the supplied 2K24 -> 2K25 -> formatter path. It does not
certify arbitrary creator models. Different eye textures keep their individual
bindings; no forced matching iris colour, UV swap or texture repaint is applied.
Different clothes retain source shaders and valid masks; missing mask coverage,
unsupported DDS layouts and geometry/weight problems remain explicit limits.
Flip's missing original mask remains unresolved. The supplied Characters.7z
collection exceeds the executor's 32 MiB transfer limit; complete 30M volumes
are needed before its models can be inspected. No result is claimed for those
unread files. Actual appearance, blood/belt behaviour and complex physics
still require targeted files and game validation.

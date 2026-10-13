# NewModelFormatter 0.14.1 experimental

This build repairs named local texture bindings for supported legacy materials,
preserves explicitly authored teeth irradiance, and automatically restores the
supplied Bryan and Flip masks for their exact inspected formatted-2K25 pairs. This
covers supported inputs that previously passed through 2K24 -> 2K25 formatting.
Gorilla-style folder input/output, CakeView, YCL translation, the original UI
logic and original source files remain preserved. Appearance still requires
an in-game check; this is not a confirmed universal eyes/teeth/beard repair.

This is a limited experimental release. Moxley's WDF layout repair preserves
his authored records, but four mismatched YWA files remain omitted. Reports
keep those failures and unavailable assets visible. No universal appearance,
clipping, belt/blood or movement fix is claimed.

## Install

1. Extract `NewModelFormatter_0.14.1_patch_installer.zip` into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`. Convert into a new empty output
   folder using your usual CakeView workflow.

Select the original Gorilla EXE, not an older experimental EXE. No Python or
Blender is needed to run the tool. The installer refuses existing output files.

## New 0.14.1 nested material paths and unknown YWA coverage

The uploaded bulk report exposed a path-check bug: output paths contained two
`Characters` folders. Gorilla's original material writer used the innermost
folder, while the native material/ocular safety helper used the outer folder.
The helper now follows the original writer's component-bounded innermost
namespace. Correct local Bryan/Flip eye tables can pass that check; genuinely
wrong references still fail. Folder inputs/outputs, mesh bytes, texture colors
and the original writers are unchanged. Ocular corrections still require their
exact supported model profiles and complete valid paired eye materials.

A plain `.ywa` file now triggers independent checked Gorilla translation of its
readable paired YCL, as known companion suffixes already did. The opaque `.ywa` remains omitted,
fingerprinted and explicitly unknown; no blob decoder, target tag or binding
records are invented. Native controlled tests use a known readable Billie YCL
with an opaque test-only companion. Jeff's actual Hat/Ponytail source YCL has
not been supplied, so its successful conversion is not claimed. Matt's actual
failed name-preservation check remains a failure pending its raw source file.

Rejected source-core reasons now appear in the model's own `problems` list as
well as the global list. Missing `J_Root` data, unreadable masks, Santino's
unidentified `Object5` body candidate and unavailable assets are not guessed.

## New 0.14 requested eye-shadow defaults

The user explicitly requested `eyeLidShadowDarkness = 1.00` and
`eyeLidShadowFallOff = 0.50` on every ordinary converted eye. These two settings
now override the legacy authored values; other supported authored settings and
texture references stay preserved. The supplied Bryan source/current output
previously had 0.10 and 0.15 in those fields. This policy is the user's requested
configuration, not an inferred Cena material calibration.

Existing native 2K26 Eye JMTLs can receive the same output-only correction.
Known missing scalar fields can be added while preserving other fields and
references; malformed or unknown layouts remain explicit failures. Missing
material files are not synthesized. Originals, eye colors, textures, geometry
and UVs remain preserved. Inspect the eye-shadow policy's before/after values
and final output hashes. In-game brightness and left/right appearance still
require testing; scalar values alone do not establish a visual fix.

## New 0.14 exposed physics binding checks

Reports distinguish YCL format translation from mesh binding and motion
validation. A read-only audit inspects bounded, supported name tables and
exposed index domains against the actual paired source and output models.
Unknown layouts, unavailable paired files and opaque solver fields remain
unverified. A declared YCL object absent from the model is reported for review;
that fact alone does not establish whether the game requires an external mesh.
No YCL, geometry or physics bytes are changed by this audit.

Moxley's ten supplied originals match the earlier report hashes. His hair
corrective data names 6,572 `M_Hair` vertices while the supplied named mesh
contains 1,060 vertices with an identity remap. Other corrective data names
6,452 `M_Combinations` vertices while that mesh has 4,358. Those declarations
already disagree with the source; Gorilla preserves the model domains.
The four YWA files remain omitted. Their authored bindings cannot be recreated
by changing counts, copying unchanged legacy blobs, or filling records with
zeros. His YCL names `746_Attire` and `S_Hair`; its solver semantics and actual
movement remain unverified even though the original translator preserves it.

The inspected native writer supports a separate WDF record-layout correction
for this exact Moxley profile. It preserves authored LOD0 records and repeats
them only for proven identical target LOD regions. All MDL, HPL and other
streams remain byte-identical. This addresses the output layout; it does not
repair opaque collider bindings or establish in-game cloth compatibility.
Unknown profiles and invalid/truncated WDF remain unsupported.

## New 0.14 bounded Cena-corresponding ocular anchors

For the exact inspected Bryan and Flip base models, Cena's eight ocular anchors
map to existing authored head vertices. Correspondence uses all 446 unique
caruncle UV identities and the complete 672-face oriented surface chart,
including equivalent quad diagonal swaps. Gorilla's generic head fallback chose
different vertices; Flip's middle pair even collapsed to the same vertex.
The bounded correction changes only eight unsigned-16 vertex-index fields,
preserving the preceding tongue anchor and every other model byte.

Only exact source/output profiles with validated paired base materials qualify.
Unknown models, different topology, failed model checks and unavailable or
failed base eye materials are excluded. The supplied Flip geometry-only fixture
lacks those materials and therefore correctly refuses the process-level patch;
it is not a complete face/appearance test. Repeated complete native inputs are
idempotent. Reports retain the mask/tongue/ocular hash chain and explicitly
require an in-game eye check. This is a correspondence correction, not a
verified universal brightness fix or a copy of Cena's eye colors/shapes.

## New 0.14 DDS mip-count correction

AJ's actual `eyelash_color.dds` declares one mip but contains exactly ten
complete mip levels through 1x1. This build corrects that count in output copies
only. Only byte 28 changes in this supplied file; every compressed pixel byte
and all ten independently decoded mip images are unchanged. The same guarded
rule applies to supported single-2D compressed DDS files only when the complete
legal chain exactly consumes the payload. Truncation, trailing bytes,
underdeclared partial chains and overdeclared counts remain rejected.
Other header fields are preserved. Inspect `mip_count_repair`, source/output
hashes, and `dds_header_normalization`. Header normalization runs after folder
copying and native dependency recovery; unexpected different output bytes are
preserved and reported. Originals remain untouched. CakeView and in-game eyelash
rendering still require checking; this does not guess eye brightness or beard
settings.

## New 0.14 one-to-one attire verification

Some AJ variants contain ring and entrance hair with identical geometry but
different names, flags and weights. The old verifier selected the first matching
geometry and compared entrance hair against ring hair. This build selects the
unique matching expected name and prevents target reuse. Ambiguous duplicates
fail verification. Genuine flag, name and weight errors remain failures. No
model, skin weights or physics are changed by this verifier correction.
The original source loop is fingerprint-guarded; unknown verifier layouts and
base-model matching keep their existing behavior.

The supplied AJ MCDs are native 2K26 outputs of variants 17-19. They prove the
separate entrance records exist, but cannot prove their weights match the
original legacy input. That requires the original 15,570,060-byte
`610_Attire.mcd` from the corresponding formatted-2K25 event folder.
AJ's shared 81,408-byte HPL remains unreadable, and these native model tails
contain empty masks. No authored full mask is reconstructed from that data.
Other rejected AJ hair/elbow DDS files have not been supplied or declared fixed.

## New 0.14 original-writer weight normalization

The exact newly supplied Kenny Omega formatted-2K25 attire has 68 tights
vertices with positive weight totals below one (minimum 0.9137255). Gorilla's
existing writer normalizes them; independently recomputed packed weights match
his supplied native output, including all eight meshes. The prior partial-rig
source gate incorrectly rejected these positive budgets before that proof.
The corrected path retains finite/nonnegative/name/positive-budget checks,
records original totals, and permits only the original writer's normalization.
It separately checks packed indices, influence limits, normalized packed values,
all written bones/parents/poses and every output weight. Input weight vectors
are not rewritten. Missing animation joints and corrupted output still fail.
The 81,408-byte Kenny HPL remains unreadable and model verification still fails
skin hiding. This correction does not recover missing masks or physics.

## New 0.13 Flip mask restoration

The new user-supplied `931_Attire.hpl` is readable and fits Flip's actual paired
Body/Head vertex remaps and topology. It contains 4,378 body IDs for both ring
and entrance modes, including all 2,097 foot/toe-dominant body vertices.
The original writer preserves those arrays across all five output LODs.
The same-stem readable sidecar can be converted normally. For the exact
inspected legacy Flip base/attire with the exact old invalid sidecar, guarded
restoration uses these supplied bytes after paired-base verification. Unknown
models sharing slot 931, missing or changed sidecars, intentional empty masks,
changed remaps and failed base verification are excluded. Native 2K26 files
do not receive this legacy fallback. Inspect `supplied_hide_mask_recovery`.
No mask IDs are estimated, and game coverage still needs checking.

Vynx's HeatSeeking clears/rebuilds selected attire weights; its HPL step is
separate. Flip's shoe weights already target surviving bones. A read-only
paired-body projection preview confirms feasible transfer, but does not
establish a clipping fix. This release restores verified mask data without
changing his shoes or Danielson's working gear. Broad automatic attire
reweighting is not supported by the current evidence.

## New 0.13 exact mouth-anchor experiments

The user confirmed that Danielson's gear works but his teeth remain black in
0.12 after a complete CakeView rebake. The supplied native 2K26 reference puts
shading-anchor slot 4 on its tongue; Gorilla's reference puts it on teeth.
Independent topology correspondence maps the native tongue vertex to vertex
127 of the exact supplied Bryan model. This build tests that anatomical role
by changing only the slot's mesh-index and vertex fields. Three bytes actually
change; the other twelve anchors and every other model byte remain identical.
Gear, masks, bones, weights, UVs, materials and texture pixels are preserved.

Only the exact inspected Bryan source/output fingerprints are eligible. The
0.12 base output SHA `9727b9f46c18eb54d4eb11a40fdf98a25d8b3ca4aac135c2b26be2714e9fad60`
becomes `19956b0ba487d68f90999d86a3837d695b3b14c0c79763d46cebc5814a1ac4ba`.
Already-ported exact matching 2K26 data can receive the same experiment, and
repeated processing is idempotent. Inspect `experimental_tongue_anchor`.
Applied or already-applied trials explicitly require an in-game teeth check.
Reports retain pre/post hashes and paired-mask verification provenance.

Flip has a separate independently verified topology match for the same tongue
role. Its exact native base SHA
`1ec8da39b5d85554b6fbcb3aa71782ebbaf665868f35e30734aa6a30c8a128dc`
becomes `8ef00213999d1921c7b0adea4dc4afa9389ea71579b43556a9ce9f84e2e0ae0b`.
Only three bytes change in that base model; his gear weights, materials and
textures stay preserved. A fresh legacy conversion qualifies only if its
actual output matches that reviewed native fingerprint.

These are guarded experiments, not established black-teeth fixes. Hammerstone
and unrelated models are excluded. No generic UV swap, teeth whitening or
shader substitution is applied.

## New 0.13 authored eye shading parameters

The supplied Blender formatter's ordinary WWE bridge uses
`MaterialGeneratorWorking.cs`. That path preserves matching source eye
materials, while Gorilla's eye conversion emitted only texture references.
The supplied MaterialEditor conversion and write schema confirm the same-key
eye scalar fields. This build retains supported finite, typed source eye
shading values in the existing shader 0x12 writer, including explicit zeros.
Unknown keys, unverified pupil aliases, invalid types and nonfinite values are
excluded. Missing source values remain missing; no brightness or color is
guessed. The original writer handles explicit zero fields without globally
changing builder behavior. Texture references, geometry, UVs and vertex colors
remain preserved. Inspect the eye preservation notes and emitted-field proof.
In-game eye brightness and left/right appearance still require testing.

Native materials that already lost these values do not contain the original
authoring data. This preservation applies during supported legacy material
conversion; it does not guess missing settings for older native ports.

## New 0.13 DDS handling

A valid compressed DDS can omit the DDSCAPS_TEXTURE bit. The supplied Blender
importer explicitly handles this game-texture header quirk. Earlier binding
checks rejected such files even when their dimensions and payload were valid.
The bit is now advisory: actual header sizes, positive dimensions, supported
formats, single 2D resources, cube/volume restrictions and every mip extent
still validate. In 0.13, accepted source and copied output bytes remained identical.
The new 0.14 guarded count repair is described above. Accepted
files record `capsTextureBitPresent` and `header_advisories`; neither pixels nor
DDS headers are rewritten by this patch. Actual CakeView baking and game
resolution remain unverified.

Binding failures now name the exact DDS file and give the rejected dimension
or flag values. This makes subsequent missing-file requests precise. Invalid,
truncated and unsupported textures remain problems and retain their old refs.

Hammerstone's supplied 0.12 report converted its base rig and passed the actual
eye/teeth link checks. It rejected the eyelash overlay and beard combo DDS
headers, but did not record those failing filenames or header bytes. Their
actual validity is not established by this report. His attire also has the
known unreadable 81,408-byte HPL; no original mask or verified embedded fallback
is available for his source fingerprints. Bryan's matching recovery profile
does not apply to Hammerstone, despite both using a `159_Attire` filename.
The original readable Hammerstone mask is still required. This DDS correction
does not claim an outfit, beard or in-game appearance repair for that case.

## Existing 0.12 checks

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
Bryan models or Flip. At the 0.11 stage, Flip's intact mask was unavailable;
the later 0.13 supplied-mask section describes his guarded restoration.

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
At the 0.11 stage, Flip's missing mask was unresolved; the later 0.13 supplied
mask is now supported for his exact inspected pair. The supplied Characters.7z
collection exceeds the executor's 32 MiB transfer limit; complete 30M volumes
are needed before its models can be inspected. No result is claimed for those
unread files. Actual appearance, blood/belt behaviour and complex physics
still require targeted files and game validation.

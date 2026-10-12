# Reported face rendering failures after 0.7

The user identified the supplied screenshots, in order, as Flip Gordon,
Xia Li, Adam Cole and Bryan Danielson. All were made with experimental 0.7.
The images show dark eyes, dark/black teeth, and speckled facial hair.
Version 0.8 adds native missing-data recovery and 2K24 routing; it does not
establish a repair for these reported visual failures.

0.9 adds actual emitted texture hashes and reference comparisons to reports.
Stored 2K26 character material observations were found in the supplied
comparison formatter's shader database. The standard teeth pair and eye normal
corroborate the reference writer constants; representative native writer tests
matched them. The original stock JMTL and texture pixels remain unavailable.
Custom input references can override those defaults and remain preserved.
An earlier Bryan report is from 0.8 and retains unreadable-HPL failures. The
latest supplied input report is from 0.9 and converts genuine 2K24 models, but
every material library is skipped with "already 2K26" and every actual-payload
audit is empty. The original reader returns no materials for all non-v3 blocks,
so this label does not establish a native format. The user reports a game crash
loading that output. Neither the format skip nor a mask failure establishes
the crash cause. 0.10 rejects unsupported material formats and retains report
problems; actual original Bryan MTLS bytes are still required for a repair.

The subsequently supplied multi-mod INPUT report is also from 0.9 but uses
12 format-41 models and converts all 12 material libraries. It records 102
actual-payload audits, four unreadable-mask failures and Xia's incomplete
physics companions. This is distinct from the earlier raw-format-40 report.
All six bases have matching left/right eye hashes and the stock eye normal.
Five teeth/mouthbag pairs match their body color/normal bindings; HBK has the
shared teeth color and a custom normal. These report facts provide no reason
to force a shared teeth pair or swap UV channels. Its limited input inventory
excludes DDS/TEX/JMTL, so missing inventory entries do not establish missing
textures. Actual pixels and game lookup remain unchecked.

The native model comparison also found two teeth UV channels on the supplied
Bryan/Xia conversions versus one on the supplied stock reference. Their first
map occupies a small texture band; the second spans the full texture. Neither
matches the stock reference's raw triangle-corner order, but these are different
models without correspondence alignment. That comparison and nearest-UV
distances do not establish that swapping channels is correct. Vertex-color ranges are
similar. No UV swap, stock-geometry substitution or blanket teeth whitening
was made from this comparison. Actual affected output model/material data and
an in-game check remain necessary to establish the rendering cause.

## What the available files establish

- The bundled Gorilla material writer is byte-identical to the supplied PWM
  reference writer: SHA-256
  `5c5e48662a40f02590cb6499e034cf23849a14f881d541bbf3fc57b680a2b944`.
- Both writers contain the same teeth global color/normal references and
  irradiance policy, and the same global eye normal reference. Their presence
  in code does not prove the generated payload, baked assets or game lookup.
- The comparison formatter's active WWE conversion selects its C# working
  material backend. Its teeth pass assigns `yCh_skin / Normal` with body atlas
  color/normal references. The alternate C# backend uses a teeth shader for
  marked WWE base models, also with body atlas references. These differ from
  the Python writer's shared stock defaults. UV0's atlas band may be intentional;
  actual affected body/teeth texture pixels are needed to test sampling.
- The supplied INPUT report maps all four eye materials to shader 0x12 and
  teeth/mouthbag to 0x1A. Those are report metadata; actual JMTL values and
  runtime resolution have not been checked for these outputs.
- Bryan's beard binding `combinations_ALPHA` is reported as hair type 1,
  shader 0x16. Adam's same-named binding comes from the source short-hair
  technique and is also reported as type 1. This does not by itself establish
  that either assignment or alpha/texture data causes the speckling.
- The supplied original Bryan model/HPL pair and Xia model pair have been
  inspected. Their current 0.7 output material payloads/textures are absent
  from this workspace. Flip/Adam's actual output model data is also absent.
- Adam Cole's supplied `combinations_ALPHA.jmtl` has a bounded shader-0x16
  type-1 payload, explicit short hair length 2, and flow/combo hashes
  `0x598227A899698A95` / `0xBE61F330147146CD`. Its pixel-mask reference is
  explicitly unbound, not an absent field. No malformed/nonfinite scalar was
  found. The user confirmed it came from Adam; the related model/textures are
  still needed before changing shader values or texture data.

## Next evidence needed

Start with Bryan's affected **0.7 converted wrestler folder** as one ZIP,
retaining `BaseModel` and `159_Default_Attire`. This should include:

- `BaseModel/baseModel.mcd`, `baseModel.mtls`, `Materials` and `Textures`;
  in particular the actual eye, teeth and mouthbag JMTLs referenced by MTLS.
- `159_Default_Attire/159_Attire.mcd`, `159_Attire.mtls`, `Materials` and
  `Textures`; in particular `Materials/combinations_ALPHA.jmtl` and its
  referenced texture assets.

The original Bryan models and HPL already supplied need not be sent again.
Inspect the actual material/texture references, channels and model shading
data before selecting a repair. Check the current game-baked files if the
converted folder proves valid. Test any supported correction structurally,
then require an in-game comparison before claiming the appearance is fixed.

## Actual formatted-2K25 Bryan archive and 0.11

The subsequently supplied 20 MiB 159_Bryan_Danielson.7z contains the actual
formatted model pair, inline v3 material libraries and 23 DDS files. Native
conversion reproduced the old unresolved named-local hashes. The DDS pixels
include tooth/gum islands and visible eye whites; tooth UV0 aligns with its
body atlas, and sampled triangle centroids are not black. Body/head normal
alpha near zero is expected metallic-channel data, not proof of corruption.

0.11 now binds those uniquely named valid local DDS assets as the supplied
comparison importer/exporter does, retaining pixels and calculating actual
output `.tex` path hashes. Globals without authoritative local assets remain.
The converter's fixed teeth RGB override also erased the original
1.0/0.75/0.75 source values; these valid per-character values are now preserved.
Exact native output verified all local eye/body/head/teeth references and the
reference-writer teeth/mouthbag bytes at RGB255/191/191. UVs, geometry and
colours remain unchanged. Beard/hair local maps participate when available,
but no beard appearance repair is confirmed.

These are supported data-conversion corrections. CakeView's baked texture
lookup, game shader sampling, anatomical shading and the photographed dark
appearance have not been reproduced in game here. The next evidence is a
fresh 0.11 bake/check using the complete original formatted source folder.

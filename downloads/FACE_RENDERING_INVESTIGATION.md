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
The newly supplied Bryan report is from 0.8, has no emitted hash audit, and
retains two unreadable-HPL failures across his regular/ROHHAIR attire folders.
Those hide-mask failures do not establish the cause of black teeth.

The native model comparison also found two teeth UV channels on the supplied
Bryan/Xia conversions versus one on the supplied stock reference. Their first
map occupies a small texture band; the second spans the full texture. Neither
matches the stock reference's triangle-corner UVs, and nearest-UV distances do
not establish that swapping channels is correct. Vertex-color ranges are
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

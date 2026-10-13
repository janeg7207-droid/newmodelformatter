# Remaining inputs for unresolved cases

The eye-shadow policy, supported DDS header correction, attire verifier and
Kenny normalization guard have been implemented and tested. The following
original data is needed to investigate remaining actual failures. Existing
uploads and originals stay preserved. In-game brightness, teeth, beard,
clipping, belt/blood and movement checks remain unperformed here.

## Jon Moxley originals received

The ten newly supplied files exactly match the original 0.13 report hashes.
The source and target meshes have identical geometry, topology, UVs and vertex
remaps. The companion declarations already disagree with the source domains:

- Hair corrective data has 6,572 sequential `M_Hair` references; the actual
  named mesh has 1,060 vertices with a dense identity remap.
- Other corrective data has 6,452 sequential `M_Combinations` references; the
  actual named mesh has 4,358 vertices with a dense identity remap.
- YCL names `746_Attire` and `S_Hair`; neither source nor target model has a
  mesh named `S_Hair`. Whether that object requires a model mesh is unverified.

The exact supplied Moxley WDF now receives a native-verified clone-LOD layout
repair, preserving his authored LOD0 records and every existing model/mask byte.
No extra copies of these ten originals are needed. Four matching authored YWA
files are still needed for a supported hair/other companion conversion:
`881_Attire.hair_ywa`, `881_Attire.hair_corr_ywa`, `881_Attire.other_ywa`,
`881_Attire.other_corr_ywa`, authored for his actual named meshes. The supplied
versions already contain the mismatched declarations; relabelling them does
not supply a safe mapping. A genuine unmodified native 2K26 attire MCD with
real hair/other YWA streams and its matching `BaseModel/baseModel.mcd` would
help verify target solver layouts, but would not supply missing authored
Moxley bindings. No invented remapping or zero bindings are used.

His actual `BaseModel/baseModel.mtls` and referenced Materials/Textures were
not included in the ten-file diagnostic and are needed for his complete face
material check. WDF solver compatibility and motion still require an in-game
check. These limits do not block the user-approved limited experimental ZIP.

## Other remaining inputs

- **AJ pack:** original formatted-2K25 `610_Default_Attire/610_Attire.mcd`
  from variant 17, 18 or 19 (15,570,060 bytes, source SHA starts `8c7124c1`);
  the uploaded 19,036,604-byte MCD is its native output. Need the actual
  affected `Textures/hair3_flow.dds`, `hair3_rai.dds`, `hair4_flow.dds`,
  `hair4_rai.dds`, `r_elbowpad_color.dds`, `r_elbowpad_nrm.dds`. Readable
  matching authored `610_Attire.hpl` is also needed for hiding; the shared
  81,408-byte placeholder cannot establish coverage.
- **Flip Gordon:** actual original `BaseModel/baseModel.mtls` and its referenced
  `BaseModel/Textures` DDS files for a complete eye/material test; actual
  `931_Default_Attire/Textures/l_elbowpad_color.dds`, `l_elbowpad_nrm.dds`,
  `r_elbowpad_color.dds`, `r_elbowpad_nrm.dds` for the four current DDS failures.
- **Kenny Omega:** a matching readable `152_Attire.hpl` from before the
  formatted-2K25 step, if one exists. The supplied source MCD/MTLS have now
  been investigated; reuploading the same 81,408-byte HPL will not supply
  readable mask data.
- **Hammerstone:** original `BaseModel/baseModel.mcd`, `BaseModel/baseModel.mtls`,
  `159_Default_Attire/159_Attire.mcd`, `159_Default_Attire/159_Attire.mtls`,
  plus a matching readable `159_Attire.hpl`. The two MTLS files are needed
  to identify the actual rejected eyelash/beard DDS filenames, which the
  older report did not record; their DDS files will then be needed.
- **Daniel Bryan '18:** original `BaseModel/baseModel.mcd` and
  `607_Default_Attire/607_Attire.mcd` used by that report, to inspect the
  missing animation root and source weights. Matching readable
  `607_Attire.hpl` is needed for hiding if available.
- **Billie:** paired original `BaseModel/baseModel.mcd` and physics data authored
  for her actual supplied hair/simulation meshes. Her existing supplied
  companions have incompatible vertex counts/indices and cannot safely be
  embedded unchanged. The known originals already supplied remain preserved.

The large Characters/Cena archive uploads exceeded the tool's 32 MiB transfer
limit and were not fully inspected. If those archives are needed for broader
coverage, complete 30 MiB split-archive volumes can be inspected; the supplied
standalone native Cena model was used for the current ocular reference.

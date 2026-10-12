# NewModelFormatter 0.9 experimental

[Download the small installer ZIP](NewModelFormatter_0.9_patch_installer.zip).

1. Extract the ZIP into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`. Use your usual folders and CakeView.
   Choose a new empty output folder. For native 2K26 repair, keep the mod's own
   folder name and include its complete BaseModel/attire folders.

0.9 corrects DXT1/BC1 alpha detection and adds actual emitted material hashes to
reports. Check `written_material_payload_audit` under material libraries and
`face_texture_check` for eyes/teeth. Reference hashes match captured 2K26
character material observations in the supplied comparison formatter. Custom
references remain preserved. Native missing-data, 2K24 inputs, Rey gear tests,
Billie case repair, Gorilla YCL and durable reports remain.

134 tests passed, including from the extracted source ZIP. Exact-build Wine
checks passed for default/caller eye/teeth material emission, BC1 classification,
available native shading-anchor indices, Billie material/YCL output and UI.
The final EXE is byte-identical to the tested candidate. Binary reconstruction
and ZIP CRC checks passed. PowerShell was not independently run on Windows here.

Black teeth, dark eyes, beard rendering and Ricochet's jacket appearance are
not confirmed fixed. His report has two trans jacket materials, no explicit
transparency variant, and an unreadable HPL. Actual DDS/model/material files
are needed to establish his screenshot's cause. The teeth models also have UV
layout differences from the stock reference; no unverified swap was made.
Reference observations do not supply original stock texture pixels or prove
game asset resolution. No shaders or physics are invented over unavailable data.

[Full installation, evidence and limitations](NEW_FORMATTER.md).
[Face investigation and needed files](FACE_RENDERING_INVESTIGATION.md).
[Source/build/test ZIP](NewModelFormatter_0.9_source_patch.zip).
[Package validation](NewModelFormatter_0.9_Package_Validation.json).
Older downloads remain available; main is unchanged.

EXE SHA-256:
`e54d28913c3f780568295a5e3e7af7071fb4120790cf2128e9e7b5c7c72884a5`

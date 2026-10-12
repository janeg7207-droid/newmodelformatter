# NewModelFormatter 0.8 experimental

[Download the small installer ZIP](NewModelFormatter_0.8_patch_installer.zip).

1. Extract the ZIP into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`. Use your usual folders and CakeView.
   Choose a new empty output folder. For existing 2K26 inputs, keep the mod's own
   folder name and include its complete BaseModel/attire folders.

This build adds native 2K24 inputs and missing-data recovery for already-ported
2K26 models. Missing material tables/entries use actual readable JMTLs. Exact
available texture references can be restored. A readable matching HPL can
restore a lost embedded mask after checking the actual paired native base.
Missing or unverified assets remain listed; no shaders or physics are invented.
Existing Rey gear tests, Billie case repair, Gorilla YCL translation and durable
final/error reports remain. Use **Open conversion report** after conversion.

114 regression tests passed, including from the extracted source ZIP. Actual-file
Wine/Xvfb tests covered native recovery, genuine Bryan 2K24 base/attire and HPL,
Rey gear, Billie YCL, AJ foot mask, error-report fallback and UI. Sources stayed
unchanged. The binary patch reconstructs the tested EXE exactly with SHA-256
checks; both ZIPs passed CRC checks. PowerShell was not independently executed
on Windows here. The unchanged CakeView gate was observed in the GUI test.

Bryan's actual model/HPL checks passed; his MTLS files were not supplied, so this
is not a complete mod validation. Xia's models contain no embedded mask and her
reported sidecar is unreadable: she needs a readable matching `982_Attire.hpl`.
Billie's WDF/YWA movement, dark eyes, AJ beard, and general belt/skin coverage
remain unresolved or require in-game checks. This build does not guarantee
that every port will be free of transparency or clipping.

[Full installation, evidence and limitations](NEW_FORMATTER.md).
[Source/build/test ZIP](NewModelFormatter_0.8_source_patch.zip).
[Package validation](NewModelFormatter_0.8_Package_Validation.json).
Older downloads remain available; main is unchanged.

EXE SHA-256:
`5ad20c8b82cd4c53f849a7cbd2775b4c6b1eb09022cbbf53db3dedaeefb20642`

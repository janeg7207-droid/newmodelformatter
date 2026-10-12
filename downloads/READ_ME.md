# Experimental NewModelFormatter 0.6 — YCL skip correction

Download `NewModelFormatter_0.6_patch_installer.zip` and extract into a fresh folder.
Run `Install.cmd` and select your ORIGINAL **Gorilla Model Formatter.exe**.
Open the created EXE and convert Billie into a new empty output folder.
CakeView, folder input/output and the original Gorilla YCL translator remain.

Readable YCL now translates even when WDF/YWA companions are unsupported.
The actual Billie result is 1,254,192 bytes and preserves its names; a fresh
independent supplied YclEditor round-trip under Wine was byte-identical.
59 regression tests and UI/native model checks passed. See
[Billie YCL validation](Billie_YCL_Conversion_Validation_0.6.json) and
[details](NEW_FORMATTER.md).

Companion conversion is still incomplete, and movement needs an in-game test.
The report will say YCL converted and retain the companion limitation. Billie's
new dark-eye report requires her original BaseModel MCD/MTLS and converted
eye_l JMTL; this build does not claim an eye fix. Rey mask repair and material
case reconciliation remain. Older downloads are retained.

`NewModelFormatter_0.6_source_patch.zip` includes the repair/build code, tests
and all supplied source/configuration snapshots, including the newly uploaded
WWE2K_MDL. The unvalidated surface-weight prototype is excluded. Full Blender
scene processing has not replaced the original native engine.

Experimental EXE SHA-256:
`7c996eeaa35a8b9cf18b0720b47bac971e9bd2c75455af582a94c8e37cbce8b7`

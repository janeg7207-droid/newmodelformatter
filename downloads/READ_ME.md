# NewModelFormatter 0.11 experimental

[Download the small installer ZIP](NewModelFormatter_0.11_patch_installer.zip).

1. Extract into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`; use your usual complete source folder, CakeView and a new empty output folder. Reconvert from the supplied formatted 2K25 source, rather than editing the old 2K26 output.

0.11 targets supported 2K24 -> formatted 2K25 -> formatter material failures: uniquely named valid local DDS files are bound to their actual copied destination paths, matching the comparison Blender formatter's image-binding workflow. Explicit valid source teeth irradiance is retained instead of Gorilla's fixed red-zero tuple. Eye, body/head, teeth, hair/beard and gear bindings participate where actual named files exist. Global/null references without authoritative local data remain preserved; no UV swapping or texture repainting occurs.

The exact supplied formatted-2K25 Bryan pair automatically gets its original readable HPL after strict input fingerprints and paired-base/remap/domain checks. All 4,215 original Body mask IDs are retained in ring/entrance at five LODs, including all 2,109 foot/toe-dominant IDs. Original files stay unchanged. Flip's original intact mask remains unavailable; no universal outfit mask is generated.

196 tests passed, including the extracted source ZIP. Exact final EXE Wine checks passed for actual Bryan conversion, all 26 local texture references, original source teeth/mouthbag irradiance bytes, mask recovery, unchanged 23 DDS copies, unchanged face geometry/UVs, final report copies, Rey mask/weights, Billie YCL/materials, unsupported-format handling and UI. Original CakeView requirements and Gorilla YCL remain. Binary reconstruction and ZIP CRC checks passed; Windows PowerShell installation and in-game appearance are untested here.

Dark or mismatched eye rendering, black teeth, beard appearance, general body/cloth clipping and belt behaviour still require game checks. A correctly written reference is not proof of a correctly baked/rendered asset. The earlier raw2K24 Bryan crash was not reproduced or established fixed; unsupported older material layouts stay explicit errors.

The larger uploaded Characters.7z collection exceeds the reader's 32 MiB transfer limit. Split a 7-Zip archive into 30M volumes and upload every part together; those unread models have not been validated.

[Full installation, evidence and limits](NEW_FORMATTER.md).
[Face investigation](FACE_RENDERING_INVESTIGATION.md).
[Source/build/test ZIP](NewModelFormatter_0.11_source_patch.zip).
[Package validation](NewModelFormatter_0.11_Package_Validation.json).

Older downloads remain available; main is unchanged.

EXE SHA-256: `a01b79b8230eb79a01fe3f326323d22b6eb42b493029543e4a85c56b515ba7a1`

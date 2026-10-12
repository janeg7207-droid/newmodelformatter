# NewModelFormatter 0.10 experimental

[Download the small installer ZIP](NewModelFormatter_0.10_patch_installer.zip).

1. Extract into a fresh folder.
2. Run `Install.cmd` and select your ORIGINAL Gorilla Model Formatter 1.0 EXE.
3. Open the created `NewModelFormatter.exe`; use your usual input/output and CakeView workflow, with a new empty output folder.

0.10 blocks unsupported material libraries previously copied as "already 2K26" and records their errors in the final reports. It can recover an existing readable embedded legacy mask only after verifying the matching converted base, unchanged Body/Head remap topology and all mask indices. Valid sidecars and Rey's existing recovery retain precedence. Original source files and existing output files are preserved; no arbitrary masks or physics are generated.

168 tests passed, including the extracted source ZIP. Exact-build Wine checks passed for controlled actual-model embedded-mask recovery, unsupported-table withholding and report persistence, original Rey mask/gear behavior, Billie materials/YCL, representative face/BC1 behavior and the UI. Uploaded original and converted Flip models were inspected; his mask remains unavailable. Binary reconstruction and ZIP CRC checks passed. The Windows PowerShell installer was not independently executed here; no in-game tests were possible.

Flip's source model/base lack a recoverable embedded mask and his supplied HPL matches the known invalid file. A readable `931_Attire.hpl` from the original mod archive before `_formatted_2K25` is still needed. This is not a confirmed Flip visibility fix. Bryan's reported game crash remains undiagnosed; his earlier raw-2K24 report skipped materials, whereas his later multi-mod 2K25 report converted them. Original raw-2K24 MTLS files are still required to test that older material layout. Eyes, teeth, beards, Ricochet's jacket and general belt coverage are not claimed visually fixed.

The later 0.9 multi-mod report records matching left/right eyes and body-atlas teeth bindings on five of six bases. These are report facts, not actual DDS/game resolution. No blanket stock-texture replacement or UV swap is justified.

[Full installation, evidence and limitations](NEW_FORMATTER.md).
[Face investigation and needed files](FACE_RENDERING_INVESTIGATION.md).
[Source/build/test ZIP](NewModelFormatter_0.10_source_patch.zip).
[Package validation](NewModelFormatter_0.10_Package_Validation.json).

Older downloads remain available; main is unchanged.

EXE SHA-256: `b92fe0349985adf7512e15df76db84b85d61b25c064f593849d23282dab16c3b`

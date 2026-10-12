# NewModelFormatter 0.7 experimental

[Download the small installer ZIP](NewModelFormatter_0.7_patch_installer.zip).
Extract into a fresh folder, run Install.cmd, and select your ORIGINAL Gorilla
Model Formatter.exe. Open the newly created NewModelFormatter.exe. Use the same
folder input/output and CakeView workflow; convert into a new empty output.

This release includes:

- Atomic final/error reports at the output root and inside the converted mod,
  a Temp fallback, and an Open conversion report button.
- A new optional paired-body gear-weight test for the exact supplied Rey model:
  tights, belt, tops, pads and wings. Enable the Rey gear checkbox to try it.
- An automatic foot-only mask for the exact supplied native AJ base/attire pair,
  without a separate HPL. Keep normal BaseModel/attire folder structure and
  select Keep the mod's own folder name.
- Retained Billie material-case repair and unchanged original Gorilla YCL
  translator. Incompatible WDF/YWA companions remain omitted.

89 regression tests passed, including from the extracted source ZIP. Actual-file
Wine checks covered the model repairs, source preservation, final report copies,
Temp error reporting, Notepad fallback and UI. The patch reconstructs the tested
EXE byte-for-byte and verifies both SHA-256 hashes. ZIP CRCs passed. The Windows
PowerShell installer was not independently executed here.

Rey movement and AJ boot coverage still require in-game checks. This is not a
universal guarantee against clipping. A belt mesh that intersects its body can
need a geometry-specific repair. AJ beard and Billie dark eyes remain unresolved.
For AJ beard, the next missing file is Materials/combinations_ALPHA.jmtl. Billie
needs her original paired BaseModel MCD/MTLS. No missing Rey physics is invented.

[Full evidence and limitations](NEW_FORMATTER.md).
[Source/build/test ZIP](NewModelFormatter_0.7_source_patch.zip).
Older downloads are retained; main is unchanged.

EXE SHA-256:
a5ddc9c25930b376d1c1cd4379f03c07a1d964fecfafe8116ce98fc1d6ace126

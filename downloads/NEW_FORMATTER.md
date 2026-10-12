# NewModelFormatter 0.4 experimental

Uses Gorilla's UI layout, readers/writers, folder workflow, and CakeView check.
Original files are preserved. Convert into a new empty output folder.

## Install on Windows

1. Extract `NewModelFormatter_0.4_patch_installer.zip` into a fresh folder.
2. Double-click `Install.cmd` and choose your ORIGINAL `Gorilla Model Formatter.exe`.
3. Open the newly created `NewModelFormatter.exe` and use your existing CakeView.

Do not select the older experimental EXE as installer input. The installer
checks the original hash and creates a separate EXE; it refuses to overwrite
an existing output. No Python or Blender installation is required.

## Changes and limits

* 2K25 conversion reconciles unique case differences between model material
  bindings and definitions, including Billie's `hair_ALPHA` / `hair_alpha`.
  Ambiguous definitions stop material output rather than guessing.
* Existing 2K26 models are accepted through a preservation/material-audit path.
  Select **Keep the mod's own folder name**. Stock-slot transplant is rejected
  because opaque texture hashes cannot yet be safely relocated. Model bytes,
  existing JMTL material payloads, and physics are preserved; unique same-length
  case differences in v6 MTLS bindings/local JMTL paths can be repaired.
  Existing 2K26 geometry, skinning, shaders, textures, and physics are not rebuilt.
  Preserved physics is explicitly unverified, not certified compatible.
* The optional Rey gear profile remaps removed bones to surviving ancestors
  for his supplied tops, shoulder pads, and wings. It defaults off and applies
  only to the exact inspected source MCD. It remains an in-game experiment.
* Guarded Rey hide-mask recovery uses the earlier readable supplied mask only
  when source attire, bad HPL, paired base hashes, body/head remap domains and
  triangle topology match the inspected profile. It retains ring/entrance masks
  separately. Any failed guard leaves the unreadable-mask error in place.
  No replacement is guessed from the corrupted mask.
* Gorilla's YCL converter remains. Billie has mismatched simulation references
  and WDF/YWA companions with no verified conversion writer. Her 2K25 physics
  conversion remains incomplete. No missing Rey physics is invented.
* No new teeth, blood, or belt repair is claimed.

Inspect the JSON report before baking. The patch identifier is
`material-binding-gear-mask-and-native26-4`. An incomplete report is not proof
of a fixed mod, and structural success does not establish in-game appearance.

## Evidence

43 regression tests passed under Python 3.14, covering material collisions,
mask recovery guards, input preservation, native 2K26 behavior and source hooks.
The 0.4 UI launched under Wine/Xvfb with CakeView required and gear mode off.
A real Billie native-2K26 model passed the bundled native reader and folder
repair smoke check: source unchanged, MCD and all 13 JMTLs byte-identical,
material library audited with no alteration needed. Separate earlier native
2K25 model checks preserved geometry/material bindings for Rey and Billie.
Gorilla's writer regenerates tangents and its original hair weighting remains.

The installer delta is reconstructed and hash-checked during packaging, and
ZIP CRCs are checked. The Windows PowerShell installer has not independently
been executed here. Wine checks are not native Windows or in-game tests.

## Still needed

For independent native validation of Rey mask recovery, the exact paired
`BaseModel/baseModel.mcd` used in his supplied conversion report is missing:
6,248,492 bytes, SHA-256
`6ac7de4ecdc79c598c3bfb6b1ea96679e5f656bae2e372053ba487eb3513155f`.
The guard tests use synthetic base geometry and do not replace that check.
The user's report established that the 81,408-byte HPL was unreadable, and the
in-game screenshot confirms visible skin through gear after the earlier patch.

After trying 0.4, inspect the report for `hide_mask_recovery`, then test Rey's
thigh coverage, tops, pads and wings during entrance and gameplay. Billie still
needs complete supported physics work and hair/cloth movement checks. Do not
use original 2K25 companions as assumed 2K26-compatible physics.

# NewModelFormatter 0.5 experimental

Uses Gorilla's UI layout, readers/writers, folder workflow, and CakeView check.
Original files are preserved. Convert into a new empty output folder.

## Install on Windows

1. Extract `NewModelFormatter_0.5_patch_installer.zip` into a fresh folder.
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
* Copied reference weight checks run on converted and preserved models. Reports
  show invalid values, absent bones, unweighted vertices, nonunit sums, driver
  influences, and over-eight influences. These are read-only diagnostics and
  do not establish anatomically correct movement.
* No new teeth, blood, or belt repair is claimed.

Inspect the JSON report before baking. The patch identifier is
`material-binding-mask-native26-reference-5`. An incomplete report is not proof
of a fixed mod, and structural success does not establish in-game appearance.

## Evidence

52 regression tests passed under Python 3.14, covering material collisions,
mask recovery guards, input preservation, native 2K26 behavior and source hooks.
The 0.5 UI launched under Wine/Xvfb with CakeView required and gear mode off.
A real Billie native-2K26 model passed the bundled native reader and folder
repair smoke check: source unchanged, MCD and all 13 JMTLs byte-identical,
material library audited with no alteration needed. Separate earlier native
2K25 model checks preserved geometry/material bindings for Rey and Billie.
Gorilla's writer regenerates tangents and its original hair weighting remains.

The installer delta is reconstructed and hash-checked during packaging, and
ZIP CRCs are checked. The Windows PowerShell installer has not independently
been executed here. Wine checks are not native Windows or in-game tests.

## Still needed

The exact 6,248,492-byte source base is now supplied and hash-matched. The
actual source base, attire and unreadable HPL ran through the bundled native
reader/writer under Wine in both 0.4 and 0.5. Base and attire verification passed;
body/head remap vectors and triangle topology were retained, and every mask
index belongs to the actual paired base. The output contains a complete
490,532-byte HPL: 10,977 body and 1,273 head entries for each ring/entrance flag
at each of five LODs, identical to the earlier readable supplied arrays.
All diagnostic input files stayed unchanged. The supplied 7,077,676-byte
reference output base is native 2K26 and also retains the body/head topology.

These isolated mask checks intentionally lacked material libraries and thus
are not a full installable mod conversion. Reference weight audits passed for
both Rey outputs and the Billie native-2K26 smoke model. In-game appearance and
movement remain untested. No additional Rey base is currently needed.

After trying 0.5, inspect the report for `hide_mask_recovery`, then test Rey's
thigh coverage, tops, pads and wings during entrance and gameplay. Billie still
needs complete supported physics work and hair/cloth movement checks. Do not
use original 2K25 companions as assumed 2K26-compatible physics.

## Reference source rebuild boundary

All six supplied Python/C#/PowerShell source files are copied unchanged into
`reference_source/`, with SHA-256 provenance. The supplied ModelFormatter's
weight audit functions are copied into `gmf_reference_checks.py` and adapted to
Gorilla's native records by `gmf_reference_audit.py`. The complete uploaded
Blender add-on is not imported into the Windows tool: its unrelated operators,
updaters and scene initialization are not needed for those checks.

This is a rebuild of the Gorilla-based experimental tool with supported
reference integration, **not a rebuilt copy of the full reference engine**.
The reference delegates actual import/export, Heat Seek, hair alignment and
HPL application to the absent **WWE2K_MDL Blender add-on**. For a full source
rebuild of that conversion path, supply its complete add-on folder/ZIP,
particularly `Blender/Extras/streamline4_1.py`,
`Blender/Extras/skeleton_alignment.py`, `Serialize/hpl_roundtrip.py`, and the
operators registering `import_vcskinmodel.load` / `export_vcskinmodel.save`.
The existing Gorilla DLL/readers/writers remain in use pending those sources;
its original YCL modules and CakeView check remain unchanged.

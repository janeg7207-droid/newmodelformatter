# NewModelFormatter 0.12 experimental

[Download the small installer ZIP](NewModelFormatter_0.12_patch_installer.zip).

1. Extract into a **new empty folder**.
2. Run `Install.cmd` and select your **original Gorilla Model Formatter 1.0 EXE**.
3. Open the created `NewModelFormatter.exe`. Keep the complete wrestler folder together; use your usual CakeView workflow and a **new empty output folder**.
4. Click **Open conversion report** when finished.

No Python or Blender is required. Original files stay unchanged. Use the original Gorilla EXE for installation, not an older experimental EXE. Existing 2K26 inputs can be audited using **Keep the mod's own folder name**.

0.12 adds guarded support for recognized compact **male** legacy rigs. It preserves Gorilla's full target builder and mapped weights, then checks core pose, every written bone/parent/matrix and every skin influence. Sample 576's 130-bone base and 97-bone attire each wrote 175 stock bones plus six custom bones; 35,838 vertices were checked. The base now passes; the attire keeps its unreadable-HPL failure. Both MCDs are byte-identical to 0.11, proving no additional geometry, shape or weight changes. Missing animation joints and malformed rigs stay unsupported.

Every recorded output gets **face_output_audit**, with coverage in **face_output_check**. Checks inspect actual eye/teeth geometry, UV/color domains, anchors, MTLS/JMTL bindings and available textures. Custom eye colors and tooth atlases are preserved. Unavailable external game assets remain unverified. The earlier native 2K26 sample informs the schema; the later 139 Cena archive remains unread.

Existing named local DDS binding, source teeth irradiance preservation, matching authored-mask recovery, BC1 alpha checks and material-case repairs remain. Vynx/PWM surface math supports the opt-in Rey gear path. Gorilla UI logic, input/output, CakeView gate and original YCL translator remain; the full Blender pipeline is not active.

**242 tests passed**, including the extracted source ZIP. Final native DLL/Wine checks passed for all six uploaded sample models, actual Bryan materials/textures/mask, Rey gear/mask, Billie YCL, report copies, format guards and UI. The wrapper-order regression has test coverage. Installer reconstruction and ZIP CRC checks passed. Windows PowerShell installation and in-game appearance remain untested here.

Dark eyes, black teeth, beards, general clothing/belt clipping and motion still need entrance/gameplay validation. Invalid/unavailable authored HPLs are not replaced with invented masks. Flip's original readable `931_Default_Attire/931_Attire.hpl` remains unavailable. Billie YCL translates, but WDF/YWA companions remain unsupported. Bryan's reported loading crash has not been reproduced or established fixed.

Characters.7z and 139_John_Cena_2019.7z exceed the 32 MiB transfer limit and remain unread. Complete 30M split volumes are needed to inspect those archives.

[Full installation and limits](NEW_FORMATTER.md). [Source/build/test ZIP](NewModelFormatter_0.12_source_patch.zip). [Package validation](NewModelFormatter_0.12_Package_Validation.json).

Older downloads remain available; main is unchanged.

EXE SHA-256: `00b4fb55e8f3b476e3deb941850aefe42b61cf44f7ad4b75a1f2b3c3c8f65fc2`

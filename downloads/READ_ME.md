# Experimental NewModelFormatter 0.5 download

Download `NewModelFormatter_0.5_patch_installer.zip` and extract into a fresh folder.
Double-click `Install.cmd` and select your ORIGINAL **Gorilla Model Formatter.exe**.
Open the created `NewModelFormatter.exe`. CakeView and folder input/output remain.
Do not use an older experimental EXE as installer input.

For existing 2K26 models, select **Keep the mod's own folder name**. This preserves
model/material/physics payloads and audits supported material bindings; it does
not rebuild geometry or certify physics compatibility.

See [NEW_FORMATTER.md](NEW_FORMATTER.md) for supported fixes and outstanding work.
52 regression tests passed. Wine UI and native-model checks passed. The supplied
original Rey base now hash-matches: actual base/attire conversion recovers the
complete mask with valid indices and unchanged source files. See
[Rey paired-base validation](Rey_Paired_Base_Mask_Validation.json).
Rey diagnostics intentionally omitted material libraries; these are mask/model
checks, not a complete installable-mod or in-game appearance test. Billie native
2K26 preservation retains MCD and 13 JMTL payloads byte for byte.

Copied reference weight checks are integrated as read-only report diagnostics.
`NewModelFormatter_0.5_source_patch.zip` contains all supplied reference source
snapshots, the repair/build code and tests. The reference's full Blender engine
cannot be rebuilt yet: it calls a separate WWE2K_MDL add-on not included in the
uploads. Gorilla YCL stays unchanged. Billie WDF/YWA conversion is unresolved.
No teeth/blood/belt repair is claimed. Windows PowerShell installer and in-game
behavior have not independently been tested here. Earlier downloads are retained.

Original EXE SHA-256:
`ece4729f2ac3fc707c69550d4a79df7866c11a61463d8eb529ae927e04f377f2`

0.5 experimental EXE SHA-256:
`e8cfb37e60f988c5bb75ab0a385476975b894e4b6f0e1d5e3d7f028ab679ba01`

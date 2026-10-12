# Experimental NewModelFormatter 0.4 download

Download `NewModelFormatter_0.4_patch_installer.zip` and extract into a fresh folder.
Double-click `Install.cmd` and select your ORIGINAL **Gorilla Model Formatter.exe**.
Open the created `NewModelFormatter.exe`. CakeView and folder input/output remain.
Do not use the older experimental EXE as installer input.

For existing 2K26 models, select **Keep the mod's own folder name**. This preserves
model/material/physics payloads and audits supported material bindings; it does
not rebuild geometry or certify physics compatibility.

See [NEW_FORMATTER.md](NEW_FORMATTER.md) for supported fixes and outstanding work.
43 regression tests passed. Wine UI and a real native-2K26 Billie preservation
smoke passed: source unchanged, model and 13 JMTLs byte-identical. Windows
PowerShell installer and in-game behavior have not independently been tested.
Rey mask recovery is guarded, requires exact paired inputs, and still lacks
independent validation with the user's 6,248,492-byte BaseModel/baseModel.mcd.
Billie WDF/YWA physics conversion remains unresolved. No teeth/blood/belt fix
is claimed. Original EXE and mod assets are not included as standalone files.

`NewModelFormatter_0.4_source_patch.zip` contains the repair modules and builders.
The earlier 0.3 download is retained for rollback.

Original EXE SHA-256:
`ece4729f2ac3fc707c69550d4a79df7866c11a61463d8eb529ae927e04f377f2`

0.4 experimental EXE SHA-256:
`be23fba112f162fbb693e24b424bdfcebdd1308ecd91f5d334abc668c1609d3b`

# Rebuild the experimental tool

Install Python 3.14 on Windows or Linux. Keep the supplied original Gorilla 1.0
EXE unchanged. From this extracted source directory run:

```
python -m pip install numpy==2.3.5
python -m unittest discover -s tests
python build_patched_exe.py "C:\path\Gorilla Model Formatter.exe" NewModelFormatter.exe --own-ui
```

NumPy is required for the surface-transfer/weight-verification tests. The EXE
already includes it, so end users do not install Python or NumPy.

The builder requires the exact original SHA-256 and a new output filename.
It reads the EXE as data, preserves its original payloads, and adds repairs.
The resulting Windows EXE retains original native DLLs, references, model
conversion, YCL code, CakeView gate and credits. It adds the own UI, material
repair, guarded mask recovery, native 2K26 preservation/material audit,
reference weight diagnostics, guarded paired-body Rey weights and final/error
report handling, plus the exact-pair AJ foot-only mask, native missing-data
audit/recovery, guarded native 2K24 folder routing, BC1 alpha checks and actual
emitted material reference reports, bounded material-format classification and
verified existing embedded-mask recovery for legacy sources, named local DDS
bindings, preserved authored teeth irradiance, per-record face output checks
and guarded partial legacy male rig admission with independent written checks. The full Blender
workflow is not active.

`reference_source/` preserves all supplied ModelFormatter, Vynx and WWE2K_MDL
source/configuration files with hashes. The nearest-triangle math and weight
checks have identified source provenance. Original mod models, textures and
Gorilla EXE are excluded. Bytecode test fixtures require Python 3.14. Native
DLL/Wine and in-game checks are separate from the regression suite.

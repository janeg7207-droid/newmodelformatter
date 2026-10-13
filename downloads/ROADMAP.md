# Mixed 2K22–2K25 batches for 0.16–0.17

User requirement: process a folder containing 2K22, 2K23, 2K24 and 2K25 models in
one run and produce 2K26 output using the existing Gorilla/CakeView workflow.

Detect each model's actual file version, not its folder name. Keep its source
year in the report and route each supported model independently. A failure
must identify the file and reason while allowing other valid models to finish.
Preserve originals and use separate output folders. Do not relabel headers or
declare skipped models converted.

2K24 and 2K25 already have conversion routes with compatibility guards. 2K22
and 2K23 need reader, rig, material, hide-mask and physics validation before
reliable support can be claimed. Older texture conventions must be inspected;
normal-map inversion must not be selected solely by a folder name. Existing
Gorilla YCL translation and unresolved companion reporting remain required.

Acceptance checks will include mixed source years in a single folder, both
model filename formats, supported male/female rigs, a rejected model among
valid inputs, matching material/texture links, durable per-model reports,
original-file preservation and entrance/gameplay checks with real samples.

Kenny Omega's supplied 2K22 files are the first validation sample for that year.
This is the target for 0.16–0.17; 0.14.2 does not establish 2K22/2K23 support.

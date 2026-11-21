# Isolated peaks in the 547/727 prime race

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24412645.svg)](https://doi.org/10.5281/zenodo.24412645)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-isolated-peaks). This repository is archived and keeps its releases and DOI.

The upper limit of the weighted prime-ideal score rounds to **175.71160384848**. If two high scores both reach 162, their log heights must be **less than one half apart or more than one billion apart**, once both log centres reach 300. Every intervening real displacement is excluded. [Exact upper limit and proof](PROOF.md)

A score above 170 stands more than 20 units above every point at log distance between $`1/2`$ and $`10^9`$ on either side. A score above 175 stands more than 40 units above those points. Both points must meet the same minimum log-centre condition. Scores above 175 occur with positive lower logarithmic density. [Peak and density calculation](peak_profile.py)

| Quantity | Certified result |
|---|---|
| Lower uniform log density of scores above 175 | At least $`2^{-48007}`$ |
| Upper uniform log density of scores at least 162 | At most $`1/(2\cdot10^9)`$ |
| Local shape near the upper limit | Every sequence approaching it has the same limiting profile on each fixed bounded interval of log displacements. |

The score is the inert-minus-split weighted sum of width two on the 547/727 field. The finite proof uses two different interval covers and a positive sum over true zero ordinates. [Verification transcript](evidence/check.txt) · [Prior work](PRIOR-WORK.md)

## Replay

Use Python 3.10+ and a C compiler with unsigned 128-bit integers. In a virtual environment run

```sh
python -m pip install -r requirements.txt
python peak_profile.py
python cover.py
python second_cover.py
python check_source.py
```

On x86-64 Linux with Git, curl, tar and zstd, `bash verify-release.sh` also checks the file hashes, upstream records and five local Lean deductions. With Lean 4.33.1 on PATH and a built Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474`, run `bash verify-release.sh /path/to/mathlib4`. An optional second argument supplies the directory of the five upstream records. The prime explicit formula and density argument are written proofs. [Lean deductions](IsolatedPeaks.lean) · [File hashes](SHA256SUMS) · [Hardy-sign certificate](https://github.com/leecrossley/theta-race-factor-400/releases/tag/v1.0.0)

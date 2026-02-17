# A Robotic Testbed for Autonomous Dump Pocket Cleaning Using Imitation Learning

**World Mining Congress 2026**

## Overview

This repository contains the project webpage for our WMC 2026 paper on autonomous dump pocket cleaning using end-to-end imitation learning. We benchmark four state-of-the-art imitation learning architectures on a low-cost SO-ARM100 robotic platform to demonstrate safe, autonomous excavation that eliminates human exposure in confined spaces.

## Project Page

**[https://brikhmp18.github.io/dump-pocket-il/](https://brikhmp18.github.io/dump-pocket-il/)**

## Key Results

Preliminary single-session evaluation (10-minute continuous autonomous operation per model, N=1). Expert baseline estimated from demonstration data (62.04 g/min × 10 min ≈ 620 g).

| Model | Removed (g / 10 min) | Rate (g/min) | % of Expert (est.) |
|-------|----------------------|--------------|---------------------|
| Expert Teleoperation (est.) | ≈ 620 | 62.0 | 100% |
| **π₀.₅ (VLA, ~3B params)** | **404** | **40.4** | **65%** |
| ACT (no pretraining) | 169 | 16.9 | 27% |
| SmolVLA (VLA, 450M params) | 113 | 11.3 | 18% |
| Diffusion Policy | 57 | 5.7 | 9% |

Notable finding: ACT removes more material than SmolVLA despite lacking pretrained representations, suggesting pretraining benefit is architecture- and scale-dependent rather than universal.

## Success Rollout Videos

Representative 10-minute autonomous sessions (muted) available on the [project page](https://brikhmp18.github.io/dump-pocket-il/).

## Resources

### Paper & Code
- **Paper:** [WMC 2026 submission](main.pdf)
- **Code:** [Training scripts (open-source IL library fork)](https://github.com/BrikHMP18/lerobot)

### Dataset
- **Dataset:** [SO-ARM100 Dump Pocket Cleaning (162 episodes, 73,944 frames)](https://huggingface.co/datasets/Autobrik/SO-ARM100-dump-pocket-cleaning2)
- **Visualizer:** [Interactive Dataset Viewer](https://huggingface.co/spaces/lerobot/visualize_dataset?path=%2FAutobrik%2FSO-ARM100-dump-pocket-cleaning2%2Fepisode_0)

### Model Checkpoints
All trained models are available on HuggingFace:
- [π₀.₅ VLA Model](https://huggingface.co/Autobrik/SO-ARM100-dump-pocket-cleaning2-pi05) — 404 g / 10 min (65% of expert estimate)
- [ACT Model](https://huggingface.co/Autobrik/SO-ARM100-dump-pocket-cleaning2-act) — 169 g / 10 min (27% of expert estimate)
- [SmolVLA Model](https://huggingface.co/Autobrik/SO-ARM100-dump-pocket-cleaning2-smolvla) — 113 g / 10 min (18% of expert estimate)
- [Diffusion Policy Model](https://huggingface.co/Autobrik/SO-ARM100-dump-pocket-cleaning2-diffusion) — 57 g / 10 min (9% of expert estimate)

## Authors

- **Brik Henrry Meza Pinedo** (PUCP, [NONHUMAN](https://nonhuman.site/))
- **Brian Pajares Correa** (PUCP, Antamina)

## Abstract

Dump pocket blockages at primary crushers cause production downtime and require manual clearing in confined spaces, leading to multiple fatalities annually from engulfment. Current autonomous approaches in mining remain limited, and the feasibility of state-of-the-art imitation learning (IL) for excavation tasks has not been systematically evaluated. This paper introduces an experimental testbed and benchmark for evaluating end-to-end IL architectures on autonomous dump pocket cleaning under controlled laboratory conditions. We benchmark four IL architectures: Action Chunking with Transformers (ACT), Diffusion Policy, and Vision-Language-Action models (π₀.₅ and SmolVLA), using a low-cost SO-ARM100 platform ($250) with granular bentonite material. In a preliminary single-session evaluation (10-minute continuous autonomous operation per model), π₀.₅ removes 404 g (40.4 g/min, approximately 65% of the expert teleoperation estimate of 620 g), while ACT removes 169 g, SmolVLA 113 g, and Diffusion Policy 57 g. Notably, ACT removes more material than SmolVLA despite lacking pretrained representations, suggesting that pretraining benefit is architecture- and scale-dependent rather than universal in this domain. Diffusion Policy is notably the slowest, consistent with its iterative denoising inference process. This work establishes a reproducible benchmark and open dataset (162 demonstrations) to support future research on autonomous confined-space operations.

## Impact

This work establishes a reproducible benchmark for AI-driven autonomy in safety-critical confined-space operations, advancing the path toward **zero-entry dump pocket maintenance** and eliminating fatal engulfment risks in mining operations.

## Citation

```bibtex
@inproceedings{meza2026autonomous,
  title={A Robotic Testbed for Autonomous Dump Pocket Cleaning Using Imitation Learning},
  author={Meza Pinedo, Brik Henrry and Pajares Correa, Brian},
  booktitle={World Mining Congress 2026},
  year={2026}
}
```

## Acknowledgments

We thank **NONHUMAN** for providing laboratory facilities and infrastructure support. We are grateful to the open-source robotics community, particularly the developers of the **SO-ARM100 platform** and the **open-source robot learning library**, whose accessible tools made this research possible. We also acknowledge **PUCP** for institutional support.

## Contact

- **Brik Henrry Meza Pinedo:** brik.meza@pucp.edu.pe
- **NONHUMAN:** https://nonhuman.site/

---

© 2026 NONHUMAN

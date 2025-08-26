# Author quick checklist

Use this checklist before submitting your artifact for evaluation.

## Essential files
- [ ] `README.md` with clear setup and usage instructions
- [ ] `LICENSE` or license information  
- [ ] Dependency specification (requirements.txt, environment.yml, Dockerfile, etc.)
- [ ] Citation information (CITATION.cff or similar)

## Core functionality
- [ ] Clear instructions for reproducing key results
- [ ] Environment and dependencies documented with version pinning
- [ ] Expected outputs or ranges documented with tolerance information
- [ ] Basic usage examples provided
- [ ] Quick test script to verify basic functionality

## Data and verification
- [ ] Sample dataset included for quick testing
- [ ] Data download scripts with checksums (for large datasets)
- [ ] Static reference outputs or expected result ranges
- [ ] Runtime estimates and hardware requirements documented

## Polish (optional but recommended)
- [ ] Clean, organized file structure
- [ ] Scripts to regenerate figures/plots
- [ ] Artifact DOI via Zenodo for permanent archival (see [`bestpractices.md`](bestpractices.md#artifact-doi-workflow))
- [ ] Professional badges showing artifact status

## Final check
- [ ] Test on a fresh clone: can someone else run it?
- [ ] All dependencies are properly specified and reproducible
- [ ] No broken paths or missing files

> **For more details:** See [`authorguide.md`](authorguide.md) and [`bestpractices.md`](bestpractices.md) for comprehensive tips and examples.

# Best practices and examples (presentation, DOI, badges)

This short guide collects practical, copy pastable tips for authors to improve artifact presentation, demos, and publishing.

## Table of Contents

- [Best practices and examples (presentation, DOI, badges)](#best-practices-and-examples-presentation-doi-badges)
  - [Table of Contents](#table-of-contents)
  - [Learning from other research artifacts](#learning-from-other-research-artifacts)
  - [Technical implementation](#technical-implementation)
    - [Polished terminal and CLI](#polished-terminal-and-cli)
    - [Rich examples (copy into `tools/` or `scripts/`)](#rich-examples-copy-into-tools-or-scripts)
    - [Reproducible environments](#reproducible-environments)
    - [Performance and debugging](#performance-and-debugging)
  - [Documentation and presentation](#documentation-and-presentation)
    - [Visuals and reports](#visuals-and-reports)
    - [Data handling and integrity](#data-handling-and-integrity)
  - [Common pitfalls to avoid](#common-pitfalls-to-avoid)
  - [Publishing and recognition](#publishing-and-recognition)
    - [Artifact DOI workflow](#artifact-doi-workflow)
    - [Badges and presentation](#badges-and-presentation)
  - [Ready to submit?](#ready-to-submit)

## Learning from other research artifacts
Browse these examples to see different approaches to artifact organization, documentation, and presentation.

- [CryptoSMT](https://github.com/kste/cryptosmt) - SMT/SAT-based cryptanalysis framework for differential cryptanalysis with clear documentation
- [Lattice Estimator](https://github.com/malb/lattice-estimator) - SageMath module for estimating concrete security of Learning with Errors instances
- [SboxAnalyzer](https://github.com/hadipourh/sboxanalyzer) - Tool for modeling cryptographic properties of vectorial Boolean functions
- [AutoGuess](https://github.com/hadipourh/autoguess) - Tool for solving the guess-and-determine problem in cryptanalysis
- [sboxU](https://github.com/lpp-crypto/sboxU) - S-box analysis and cryptographic properties evaluation tool
- [ZeroPlus](https://github.com/hadipourh/zeroplus) - Tool for finding impossible-differential, zero-correlation and integral attacks
- [MPT](https://github.com/hadipourh/mpt) - Tool for finding integral distinguishers and key recovery attacks using mixed-integer programming

## Technical implementation
Practical techniques to improve your artifact's usability and reliability.

### Polished terminal and CLI
Improve user experience with better terminal output and command-line interfaces.

- Use Python's [Rich](https://rich.readthedocs.io/) (or [Textual](https://textual.textualize.io/) for terminal UIs) to add color, pretty tables, progress bars, and clearer tracebacks.
- CLI frameworks: [Click](https://click.palletsprojects.com/) or [Typer](https://typer.tiangolo.com/) (Python), [Clap](https://github.com/clap-rs/clap) (Rust), [Cobra](https://github.com/spf13/cobra) (Go) give consistent help text and argument parsing.
- Consider providing clear examples or demos that reviewers can easily run to see your artifact in action.

### Rich examples (copy into `tools/` or `scripts/`)
```python
from rich.console import Console
from rich.table import Table

console = Console()
table = Table(title="Sample Results")
table.add_column("Metric")
table.add_column("Value")
table.add_row("Accuracy", "0.92")
table.add_row("F1", "0.88")
console.print(table)
```

```python
from rich.progress import track
import time

for i in track(range(5), description="Running tasks"):
    time.sleep(0.2)
```

### Reproducible environments
Ensure reviewers can run your artifact reliably across different systems and setups.

- Pin dependencies. Provide `requirements.txt` or `environment.yml` with versions, and note OS and tool versions.
- Prefer containers for portability. Include a `Dockerfile` and a short note on how to build and run.
- Include a quick test to verify everything works (e.g., `./test.sh` or `python -m pytest tests/`)
- Control randomness. Set fixed random seeds and document expected tolerances for results.
- Control parallelism. Document CPU/GPU requirements and environment variables like `OMP_NUM_THREADS` when relevant.

### Performance and debugging
Help reviewers understand resource requirements and troubleshoot issues efficiently.

- **Memory monitoring**: `python -m tracemalloc` or `@profile` decorator with `memory_profiler`
- **Runtime estimates**: Include expected runtime for major operations in your README
- **Verbose modes**: Add `--verbose` or `--debug` flags that show progress and intermediate results
- **Resource limits**: Document minimum RAM/disk requirements and provide lighter test datasets
- **Basic testing**: Include a quick verification script (e.g., `./test.sh` or `python -m pytest tests/`)

```python
# Quick memory check
import psutil
print(f"Available RAM: {psutil.virtual_memory().available / 1e9:.1f} GB")
```

```bash
#!/bin/bash
# test.sh - quick verification script
if [ ! -f "data/input.csv" ]; then
    echo "Error: Missing data/input.csv. Run: python download_data.py"
    exit 1
fi
echo "✓ Basic checks passed"
```

## Documentation and presentation

### Visuals and reports
Make results clear and reproducible with proper visualization and documentation.

- Provide scripts to regenerate plots ([Matplotlib](https://matplotlib.org/)/[Seaborn](https://seaborn.pydata.org/), [Plotly](https://plotly.com/python/), [Altair](https://altair-viz.github.io/)). Commit a static PNG/PDF version for reference.
- For notebooks, include a runnable `.ipynb` and optionally export an HTML view ([NBViewer](https://nbviewer.org/) or [Voilà](https://voila.readthedocs.io/)) for an interactive demo.
- Produce a short HTML or PDF summary ([nbconvert](https://nbconvert.readthedocs.io/), [pandoc](https://pandoc.org/)) that shows the key outputs, version info, and exact commands used.

### Data handling and integrity
Ensure data is accessible, verified, and properly documented for reviewers.

- Provide download scripts for large data with checksums (e.g., `sha256sum`) and verify on download.
- Include a small sample dataset for quick tests and document how to fetch the full data.
- Describe the data schema, provenance, and licensing clearly.
- Consider [Git LFS](https://git-lfs.com/) or [DVC](https://dvc.org/) for large files and data versioning.

## Common pitfalls to avoid
Prevent common issues that frustrate reviewers and cause evaluation failures.

- Missing dependencies: virtual environments and containers prevent this
- Broken paths: test your artifact on multiple systems or inside containers  
- Insufficient documentation: provide runtime estimates and hardware requirements
- Large downloads without verification: include checksums and sample data for testing

> **Tip:** For a comprehensive preparation workflow, see [`authorguide.md`](authorguide.md) for detailed guidance on artifact preparation and submission.

## Publishing and recognition

### Artifact DOI workflow
Create a permanent, citable reference for your artifact to enhance its academic impact.

**Why create an artifact DOI?**
- **Permanent archival**: Zenodo guarantees long-term preservation; artifacts cannot be removed from the public domain
- **Stable access**: Reviewers and future researchers can always access your artifact via the DOI
- **Professional credibility**: DOIs enhance the academic legitimacy and citability of your work
- **Version tracking**: Each release gets its own DOI while maintaining a concept DOI for the overall project

**GitHub + Zenodo quick workflow:**
1. Create a GitHub release when your artifact is stable
2. Link your repository to [Zenodo](https://zenodo.org) via GitHub integration
3. Zenodo automatically creates a DOI for each release
4. Include the DOI in your paper and artifact README
5. Add `CITATION.cff` file to your repository for proper attribution

**GitHub release steps:**
1. Tag your final commit: `git tag v1.0.0 && git push --tags`
2. Go to GitHub → Releases → "Create a new release"
3. Choose your tag, add release notes describing the artifact
4. Zenodo will automatically archive and assign a DOI

**Alternative artifact DOI providers:**
- [Figshare](https://figshare.com/)
- [OSF](https://osf.io/)
- Institutional repositories

> **Note:** All reputable DOI providers offer permanent archival - once published, your artifact becomes a permanent part of the scholarly record and cannot be removed.

**Professional presentation:**
```markdown
## Citation
If you use this artifact, please cite:

[Author Names]. "Paper Title." Conference/Journal, Year.
DOI: https://doi.org/10.xxxx/xxxx

**Artifact:** https://doi.org/10.5281/zenodo.xxxxxx
```

**Timing for ToSC:**
- **Create artifact DOI before submission**: Generate your artifact DOI and include it with your artifact submission
- **Permanent archival commitment**: Remember that Zenodo DOIs create permanent archives - your artifact will remain publicly accessible indefinitely

### Badges and presentation
Add visual indicators to communicate artifact status and enhance professional appearance.

Use [shields.io](https://shields.io) badges to show artifact status and DOI. Prefer `style=flat`, avoid emojis in labels, and keep visuals minimal.

**Artifact evaluation badges:**
```markdown
![Artifacts Available](https://img.shields.io/badge/Artifacts-Available-2da44e?style=flat&labelColor=2b2b2b)
![Artifacts Functional](https://img.shields.io/badge/Artifacts-Functional-007ec6?style=flat&labelColor=2b2b2b)  
![Results Reproduced](https://img.shields.io/badge/Results-Reproduced-fe7d37?style=flat&labelColor=2b2b2b)
```

**Artifact DOI and license badges:**
```markdown
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.xxxxxx.svg)](https://doi.org/10.5281/zenodo.xxxxxx)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
```

**Tips:**
- Keep badges minimal and place them near the top of `README.md` if you choose to use them
- An artifact DOI is optional but helps citability; see the DOI workflow section above for creation steps

## Ready to submit?
Use the comprehensive checklist to ensure your artifact is ready for evaluation: [`authorchecklist.md`](authorchecklist.md)

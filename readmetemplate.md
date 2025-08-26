# Artifact README Template

This template provides a structure for your artifact README. Adapt sections as needed for your project.

## Overview

Provide essential information about your artifact and its connection to your paper.

**Paper:** [Paper Title]  
**Authors:** [Author Names]  
**Artifact:** [Brief description of what this artifact contains and supports]

## Requirements

Help users understand what they need to evaluate your artifact.

**Hardware:** [e.g., 8GB RAM, 50GB disk space]  
**Software:** [e.g., Python 3.9+, Docker, or specific tools]  
**Estimated time:** [e.g., Setup: 15 min, Basic test: 30 min, Full evaluation: 2-4 hours]

## Quick Start

Provide simple steps for users to get your artifact running quickly.

```bash
# 1. Clone and setup
git clone [your-repo-url]
cd [artifact-directory]

# 2. Environment setup (choose one)
pip install -r requirements.txt
# OR conda env create -f environment.yml
# OR docker build -t myartifact .

# 3. Basic test
python main.py --help
python main.py --test
```

## File Structure

Explain your artifact's organization to help users navigate.

```
artifact/
├── README.md              # This file
├── LICENSE                # License file
├── requirements.txt       # Dependencies (or environment.yml)
├── src/                   # Source code
├── data/                  # Input data or download scripts
├── scripts/               # Helper scripts (optional)
└── results/               # Reference outputs (optional)
```

## Usage and Experiments

Guide users through using your artifact and reproducing key results.

### Basic Usage
Describe what users should see when running basic commands.

Example: "Running `python main.py --test` should complete in 2-3 minutes and display a summary table of test results."

### Main Experiments
Describe the key experiments that support your paper's claims.

- **Experiment 1:** [Description and expected output]
  - Command: `[specific command to run]`
  - Expected output: `[what files/results are generated]`
  - Runtime: `[estimated time]`

- **Experiment 2:** [Description and expected output]
  - Command: `[specific command to run]`
  - Expected output: `[what files/results are generated]`
  - Runtime: `[estimated time]`

- **Expected results:** Document any performance ranges, numerical tolerances, or variations that users should expect.

### Claims Supported (Optional)
If helpful for users, explicitly connect your artifact to specific paper claims.

- [Claim 1: e.g., "Performance results in Table 2"]
- [Claim 2: e.g., "Algorithm comparison in Figure 3"]

## Troubleshooting (Optional)

Help users resolve common issues they might encounter.

**Common issues:**
- [Issue 1]: [Solution or workaround]
- [Issue 2]: [Solution or workaround]

**Getting help:** [Contact information or link to issue tracker]

## Additional Resources

For more guidance on artifact presentation and publishing, see [`bestpractices.md`](bestpractices.md).

## License

Specify your artifact's license to clarify usage rights.

[Specify your license, e.g., MIT, Apache 2.0, etc.]

## Citation

Provide citation information to help others properly credit your work.

Choose the format that works best for your project:

**BibTeX (for LaTeX/academic papers):**
```bibtex
@article{yourpaper2024,
  title={Your Paper Title},
  author={Author Names},
  journal={Conference/Journal Name},
  year={2024},
  doi={10.5281/zenodo.1234567}  % replace with your artifact DOI if available
}
```

**CITATION.cff (recommended for repository metadata):**
See [Citation File Format](https://citation-file-format.github.io/) for more details.

```yaml
cff-version: 1.2.0
title: Artifact for [Your Paper Title]
authors:
  - family-names: [LastName]
    given-names: [FirstName]
    affiliation: [Your Institution]
date-released: [YYYY-MM-DD]
version: 1.0.0
url: https://github.com/yourusername/yourrepo
license: MIT
abstract: Brief description of what this artifact contains and supports.
doi: 10.5281/zenodo.1234567  # replace with your artifact DOI if available
```

**Simple citation (for plain text references):**
```
[Author Names]. "Paper Title." Conference/Journal Name, Year.
Artifact: https://github.com/yourusername/yourrepo
DOI: 10.5281/zenodo.1234567 (if available)
```

## Contact

Provide a way for users to reach you with questions.

For questions about this artifact: [your-email@domain.com]

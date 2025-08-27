# Artifact Guide for Authors

**Ship a clean, runnable artifact for evaluation. The key is making it easy for users to understand and use your work.**

## Minimum Requirements

**Artifacts that do not meet these requirements will be rejected without detailed review:**

1. **README.md** with setup instructions and usage examples
2. **License** file or clear license statement
3. **Dependencies** specified (requirements.txt, Dockerfile, etc.)
4. **Runnable code/data** (not just documentation)
5. **Paper connection** clearly stated

**Additionally, artifacts requiring more than 4 hours setup time or completely broken functionality may be rejected during review.**

## Table of Contents

- [Artifact Guide for Authors](#artifact-guide-for-authors)
  - [Minimum Requirements](#minimum-requirements)
  - [Table of Contents](#table-of-contents)
  - [What you might include](#what-you-might-include)
  - [Badges](#badges)
  - [Essentials for a good artifact](#essentials-for-a-good-artifact)
  - [One possible structure (adapt as needed)](#one-possible-structure-adapt-as-needed)
  - [Preparation Steps](#preparation-steps)
    - [1. **Documentation**](#1-documentation)
    - [2. **Environment and Dependencies**](#2-environment-and-dependencies)
    - [3. **Helpful tools for better artifacts**](#3-helpful-tools-for-better-artifacts)
    - [4. **Data and Code organization**](#4-data-and-code-organization)
  - [Hosting and Submission](#hosting-and-submission)
    - [Submission packaging and required metadata](#submission-packaging-and-required-metadata)
    - [Licensing and redistribution permission](#licensing-and-redistribution-permission)
    - [Hosting, confidentiality and tracking](#hosting-confidentiality-and-tracking)
    - [Packaging recommendations (practical)](#packaging-recommendations-practical)
    - [Data artifacts](#data-artifacts)
    - [During review: updates and changelogs](#during-review-updates-and-changelogs)
  - [Ready to submit?](#ready-to-submit)

## What you might include

Your artifact can be **code**, **datasets**, **analysis scripts**, **configurations**, **notebooks**, Docker images, and post processing tools.

**Examples of research artifacts (not requirements):**

- **Implementation artifacts**: Source code, libraries, tools, and experimental frameworks
- **Dataset artifacts**: Specialized data collections, test instances, benchmark datasets, experimental data  
- **Analysis artifacts**: Jupyter notebooks with computational analysis, plotting scripts, statistical analysis tools
- **Hybrid artifacts**: Complete experimental setups combining code, data, and analysis workflows

> **Note:** For inspiration from excellent research artifacts in cryptography and other domains, see the examples in [`bestpractices.md`](bestpractices.md#learning-from-other-research-artifacts).

 

**For dataset artifacts** (e.g., specialized data collections, test instances, benchmark datasets):

- Include clear **metadata** describing the dataset structure, generation method, and properties
- Provide **viewing or analysis tools** or scripts to explore and validate the dataset
- Include **format documentation** explaining file structures and data encoding
- Add **verification scripts** to check dataset integrity and properties mentioned in the paper

## Badges

- **Available**: Publicly retrievable via stable link (a DOI is optional but recommended for citability)
- **Functional**: Works as described with good documentation and completeness
- **Reproduced**: Main results independently verified

## Essentials for a good artifact

- **Clear README**: explain what your artifact does and how to use it
- **Simple usage**: provide examples of how to run your tool or reproduce key results
- **Reproducible environment**: include dependency information (requirements.txt, environment files, or containers)
- **Expected results**: describe what outputs reviewers should expect to see

## One possible structure (adapt as needed)

```
artifact/
├── README.md
├── LICENSE  
├── [dependency file]      # requirements.txt, environment.yml, etc.
├── src/ or code/          # Source code
├── data/ or datasets/     # Input data or download scripts
├── [scripts/]             # Optional: helper scripts
└── [results/]             # Optional: reference outputs
```

**Important**: This is just one example. Use whatever structure makes sense for your project. The key is clear organization and documentation.

## Preparation Steps

### 1. **Documentation**

- **README.md**: Clearly state which paper claims your artifact supports and provide simple usage examples
- **Installation**: Provide step by step setup instructions
- **Usage**: Show how to run your tool with example commands and explain any important options
- **Expected outputs**: Describe what files or results your tool produces
- **Time estimates**: Give rough ideas of how long things take to run
- **Document as you go**: Write documentation while you are building, and include examples and common use cases
- **Design for users**: Imagine someone else (or future you) trying to use your tool and address likely questions

### 2. **Environment and Dependencies**

- **Version control**: Use meaningful commit messages, tag important versions or releases, and avoid committing large binaries or sensitive data
- **Dependencies**: List all required packages and versions (requirements.txt, environment.yml, or Dockerfile)
- **Containers**: [Docker](https://docs.docker.com/) is often the easiest way to ensure your artifact works across different systems
- **Testing**: Try running your artifact on a clean machine or fresh container, and on different systems when possible, to catch missing dependencies or configuration issues

### 3. **Helpful tools for better artifacts**

- **Command line interfaces**: Tools like Python's [Click](https://click.palletsprojects.com/) or the standard library's [argparse](https://docs.python.org/3/library/argparse.html) make it easy to add `--help` and handle arguments cleanly
- **Progress and output**: Libraries like [Rich](https://rich.readthedocs.io/) can make your tool's output much nicer with progress bars, tables, and colors
- **Data handling**: For large datasets, provide download scripts with checksums rather than committing huge files
- **Prefer standard tools**: Leverage established libraries and data formats rather than reinventing components
- **Learn from others**: Review artifacts from previous venues to see what works well and adapt good patterns

If you build a custom tool for your experiments, keep the interface simple and predictable. Use [`authorchecklist.md`](authorchecklist.md) for final verification and [`bestpractices.md`](bestpractices.md) for detailed examples.

### 4. **Data and Code organization**

- **Code structure**: Organize your code logically with meaningful file and directory names
- **Small datasets**: Include small datasets (< 100MB) directly in your repository with clear documentation
- **Large datasets**: For large datasets, provide download scripts with checksums and clear instructions
- **Dataset only artifacts**: For pure dataset submissions, include comprehensive metadata, format specifications, and analysis or viewing tools
- **Dataset documentation**: Always include schema descriptions, generation procedures, and validation methods
- **Licensing**: Include appropriate licenses for your code and data, clearly documenting any third party components
- **Reproducibility**: Consider what someone would need to reproduce, validate, or extend your work

**Special considerations for dataset artifacts:**

- **Mathematical data collections**: Include clear representations, property descriptions, and verification scripts
- **Test datasets**: Provide clear input/output format documentation and validation tools
- **Benchmark instances**: Include difficulty ratings, expected solution methods, and timing baselines
- **Experimental data**: Document collection methodology, preprocessing steps, and statistical properties

## Hosting and Submission

**For artifact evaluation**: [GitHub](https://github.com/) release, institutional repository, or stable share link. 
Consider creating a DOI for your artifact via [Zenodo](https://zenodo.org/) (optional but recommended for citability, professional presentation, and permanent archival).

> **Tip:** For step-by-step instructions on creating a DOI for your artifact using GitHub and Zenodo, see the detailed workflow in [`bestpractices.md`](bestpractices.md#artifact-doi-workflow).

**Submission**: Via conference artifact evaluation system with accepted paper info, artifact abstract, and contact details

### Submission packaging and required metadata

When you register/submit the artifact to the conference evaluation system include the following in your submission package or metadata:

- Title and abstract of the accepted paper (or camera ready PDF if available)
- Authors and affiliations, and contact email(s) for the artifact
- A short description of the artifact contents and what it supports
- If the artifact is ≤20 MB: include a `.zip` or `.tar.gz` snapshot of the artifact
- If the artifact is >20 MB: provide clear instructions for obtaining the artifact (stable URLs, access instructions, checksums)
- A link to a repository (e.g., [GitHub](https://github.com/)) and the exact commit/tag used for the submission

### Licensing and redistribution permission

- Many conferences require permission to distribute archived artifacts. Include an open source license (OSI approved preferred) in the repository root.
- If your artifact contains third party materials, ensure you have the right to redistribute those components and document their licenses.
- If any component cannot be redistributed (commercial software, proprietary datasets), clearly document the limitation and provide instructions to obtain/access the required components.

### Hosting, confidentiality and tracking

- Prefer stable public hosting (GitHub releases, Zenodo, institutional repositories) and avoid hosting artifacts on personal websites.
- Do not embed analytics or tracking elements in artifact hosting pages or downloadable content; these can deanonymize reviewers and violate the single blind review model.

### Packaging recommendations (practical)

- Provide source code and build scripts as the primary form. For complex dependencies also provide one or more of:
  - A Docker image plus the `Dockerfile` used to build it (preferred)
  - A VM image ([VirtualBox](https://www.virtualbox.org/), QCOW) and the script used to create it
  - A binary package (RPM/DEB/MSI) when appropriate
  - A short video demonstrating usage or results (helpful for heavy or commercial or hardware dependent artifacts)
- Include scripts to download large datasets with checksums and a short README explaining the data schema and any preprocessing steps.

### Data artifacts

- For dataset artifacts (specialized data collections, test instances, experimental data), prefer common machine readable formats (CSV, JSON, XML, HDF5) and include comprehensive metadata describing the schema, generation method, and provenance.
- **Mathematical datasets**: Include appropriate representations, standard formats, and verification scripts to check key properties mentioned in your paper.
- **Test collections**: Use standardized formats where possible and include validation scripts that verify expected properties.
- **Benchmark collections**: Include difficulty metrics, expected solution approaches, and baseline performance measurements.
- If non standard formats are used, include viewing or conversion tools, format documentation, and examples so reviewers can inspect and understand the data structure.
- Always include a dataset **validation script** that verifies the integrity and claimed properties of your dataset.

### During review: updates and changelogs

- Most artifact review processes are collaborative and authors may update artifacts while under review. If you update the artifact, clearly document changes in a changelog.
- If updates materially affect scientific results (performance, correctness), clearly call out those changes in the submission notes and changelog.

## Ready to submit?

Before submitting your artifact for evaluation, verify you meet the minimum requirements listed at the top of this guide. Use the verification checklist: [`authorchecklist.md`](authorchecklist.md)

For additional examples and advanced techniques, see [`bestpractices.md`](bestpractices.md).

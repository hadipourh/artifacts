# Artifact Guide for Reviewers

A comprehensive guide for evaluating research artifacts and determining badge awards.

## Table of Contents

- [Overview](#overview)
- [Badge Criteria](#badge-criteria)
  - [Artifacts Available](#artifacts-available)
  - [Artifacts Functional](#artifacts-functional)
  - [Results Reproduced](#results-reproduced)
- [Evaluation Process](#evaluation-process)
- [Review Guidelines](#review-guidelines)
- [Documentation](#documentation)

## Overview

Artifact evaluation focuses on **technical merit, not novelty**. Your goal is to assess whether others can access, run, and verify the artifacts relative to the paper's claims.

**Badge Summary:**
- **Available:** Publicly retrievable via stable link (DOI optional but recommended)
- **Functional:** Works as described with good documentation and completeness  
- **Reproduced:** Main results independently verified

**Minimum Requirements Check:** Before detailed evaluation, verify the artifact has: README.md, license, dependency specification, runnable code/data, and clear paper connection. Recommend rejection if any are missing.

## Badge Criteria

Evaluate artifacts across three dimensions, each with specific requirements.

### Artifacts Available

Assess whether the artifact is publicly accessible with necessary materials.

**Requirements for Pass:**
- Artifact is publicly retrievable via stable link (DOI optional but recommended for citability)
- Basic materials present: README, license, code/data access
- Instructions exist for setup and execution

**Assessment scale:**
- Fully accessible / Partially accessible / Not accessible

**Fails if:** Broken links, no public access, or missing essential files

### Artifacts Functional

Evaluate the artifact's usability and completeness across multiple dimensions.

**Assessment dimensions:**
1. **Documentation quality:** Clear README, setup instructions, expected outputs, resource requirements
   - Excellent / Very good / Good / Fair / Poor
   
2. **Completeness:** All necessary code, data, configs, and scripts present
   - Complete / Partially complete / Incomplete
   
3. **Exercisability:** Setup succeeds, smoke test works, main pipeline runs
   - Very easy / Easy / Moderate / Difficult / Could not run

**Award criteria:** Generally good performance across dimensions with no major blocking issues

### Results Reproduced

Determine whether independent execution produces results that match the paper's claims.

**Requirements for Pass:**
- Independent execution produces results where main results match within acceptable tolerance
- Bit-for-bit identity only required if explicitly claimed by authors

**Additional assessment - Reusability:**
- Highly reusable / Minor effort needed / Significant effort / Not reusable / Not applicable

**Evaluation process:**
1. Run declared configurations (reduced scale acceptable)
2. Use authors' post-processing scripts
3. Compare results with paper claims  
4. Document any discrepancies and reusability assessment

## Evaluation Process

Follow this structured approach to systematically evaluate artifacts.

### 1. Initial Review (30-45 minutes)
Get oriented with the artifact and assess your capability to review it.

- Check that the artifact is accessible and has basic documentation
- Read the README to understand what the artifact does and how to use it  
- Assess whether you have the resources needed (time, hardware, software)
- Verify basic submission metadata and licensing information

### 2. Environment Setup (30-90 minutes)
Establish a working environment following the authors' instructions.

- Follow the installation instructions provided by the authors
- Set up the required environment ([Docker](https://docs.docker.com/), conda, etc.)
- Note any issues or missing information for feedback

### 3. Basic Testing (flexible timing)
Verify the artifact's basic functionality before deeper evaluation.

- Try running the artifact with the provided examples
- Test that it produces the expected types of outputs
- Use your judgment about testing scope based on complexity and available time

### 4. Main Evaluation (1-3 hours)
Conduct the core assessment of the artifact's claims and functionality.

- Run experiments as described in the paper, adapting scope as needed
- For long-running experiments, consider using smaller datasets or fewer iterations
- Document what you tried and what worked or didn't work
- Compare outputs with the paper's claims where feasible

### 5. Report Writing (30-60 minutes)
Document your findings and provide constructive feedback.

- Summarize what you attempted and what worked
- Provide constructive feedback to help authors improve their artifacts
- Make badge recommendations based on your experience
- Assess overall merit: Strong accept / Accept / Weak accept / Weak reject / Reject
- Note your reviewer expertise level: Expert / Knowledgeable / Some familiarity / No familiarity

## Review Guidelines

Best practices for conducting professional and effective artifact reviews.

### Professional Conduct

**Be constructive and helpful:**
- Focus on providing actionable feedback to help authors improve their artifacts
- Identify specific issues and suggest practical solutions when possible

**Maintain anonymity:**
- Do not reveal your identity through comments or commits
- Use the official artifact evaluation system for all communications

**Communicate professionally:**
- Provide clear, respectful feedback in your reviews
- Ask questions through proper channels when clarification is needed

**Be reasonable in expectations:**
- Authors cannot fix fundamental algorithmic limitations during review
- Focus on documentation, usability, and reproducibility improvements

**Allow for updates:**
- Authors may update artifacts during review to address issues
- Request a changelog if major changes might affect your evaluation

### Confidentiality and Ethics

**Protect author privacy:**
- Do not attempt to deanonymize authors through artifact inspection
- Report any hosting that includes tracking or analytics to the review chairs

**Use appropriate access methods:**
- Prefer stable hosting ([GitHub](https://github.com/) releases, [Zenodo](https://zenodo.org/)) over personal pages
- Avoid methods that might leak access logs or compromise anonymity

### Timeline and Reporting

**Review completion:**
- Aim to complete reviews within the conference timeframe (typically 7-8 weeks)
- Communicate early if you encounter major blocking issues

**Documentation requirements:**
- Record the exact commit/tag you tested for reproducibility
- Note whether you used reduced scale runs or modified parameters
- Provide sufficient detail for authors to understand and address feedback

## Documentation

Use the structured evaluation form to ensure comprehensive and consistent reviews.

**Required documentation:** Use [`reviewerform.md`](reviewerform.md) to record your evaluation, including:

- Artifact summary and metadata
- Environment and setup details
- Commands executed and results obtained
- Badge recommendations with clear justifications  
- Constructive feedback for authors

**Best practices:**
- Fill out the form progressively during your evaluation
- Record exact commands and any modifications you made
- Document both successes and failures for complete feedback
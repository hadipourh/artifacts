# Artifact Review Form

**Instructions:** Fill out this form completely during your artifact evaluation. Replace placeholder text in brackets with your specific information.

Offline submission: If your venue uses the IACR-style offline form, use `reviewerform.txt`. 
Do not change lines that start with `==+==` or `==*==`; fill in the marked fields and upload per the venue instructions.

## Table of Contents

- [Artifact Summary](#artifact-summary)
- [Artifact Metadata](#artifact-metadata)
- [Evaluation Environment](#evaluation-environment)
- [Badge Evaluation](#badge-evaluation)
- [Detailed Evaluation](#detailed-evaluation)
- [Overall Assessment](#overall-assessment)
- [Comments for Authors](#comments-for-authors)
- [Comments for Program Committee](#comments-for-program-committee)

---

**Paper:** [Paper title]  
**Paper ID:** [ID if applicable]  
**Reviewer:** [Name or identifier]  
**Date:** [YYYY-MM-DD]  
**Review Status:** [Draft / Ready for submission]
**Commit/Tag tested:** [e.g., v1.0.0 or abc1234]  
**Reduced scale runs used:** [Yes/No, brief notes]

---

## Artifact Summary

[Brief description of what the artifact contains and what you evaluated - 2-3 sentences]

## Artifact Metadata

- **Artifact location:** [URL / DOI]
- **License included:** ☐ Yes (license file present) ☐ No (missing) ☐ Not sure (unclear)
- **Primary language/platform:** [e.g., Python 3.9, C++17, MATLAB R2023a]
- **Environment requirements:** [e.g., Linux, GPU, specific hardware]

## Evaluation Environment

- **Operating system:** [e.g., Ubuntu 22.04, macOS 14.1, Windows 11]
- **Hardware:** [e.g., Intel i7-12700K, 32GB RAM, RTX 4080]
- **Container/virtualization:** [Docker image, VM, conda environment, etc.]
- **Special requirements:** [clusters, specific hardware, etc.]

## Badge Evaluation

**Available Badge — Artifact accessibility**
☐ Awarded ☐ Not awarded

- **Accessibility (pick one):**
	- ☐ Fully accessible — public link works; files retrievable without special access
	- ☐ Partially accessible — some parts restricted/missing or extra undocumented steps needed
	- ☐ Not accessible — broken links or permissions prevent retrieval
- **Justification:** [How easily could you access the artifact?]

**Functional Badge — Artifact functionality**  
☐ Awarded ☐ Not awarded

- **Documentation quality (pick one):**
	- ☐ Excellent — clear README, setup, usage, and expected outputs
	- ☐ Very good — minor gaps but easy to follow
	- ☐ Good — generally clear with a few ambiguities
	- ☐ Fair — unclear sections or missing context
	- ☐ Poor — insufficient documentation
- **Completeness (pick one):**
	- ☐ Complete — all code/data/configs/scripts needed are present
	- ☐ Partially complete — minor elements missing or partial coverage
	- ☐ Incomplete — key components missing; blocks evaluation
- **Ease of use / Exercisability (pick one):**
	- ☐ Very easy — straightforward setup; worked without issues
	- ☐ Easy — minor setup quirks; overall smooth
	- ☐ Moderate — needed some troubleshooting but worked
	- ☐ Difficult — unclear or error prone setup; significant intervention
	- ☐ Could not run — unable to execute
- **Justification:** [Does the artifact run and behave as described?]

**Reproduced Badge — Results reproduction**
☐ Awarded ☐ Not awarded

- **Reproducibility (pick one):**
	- ☐ Fully reproduced — main results match within acceptable tolerance
	- ☐ Partially reproduced — some key results reproduced; others not
	- ☐ Not reproduced — attempted but could not reproduce
	- ☐ Not attempted — did not try (e.g., time, complexity)
- **Reusability (pick one):**
	- ☐ Highly reusable — well organized, modular, clearly documented
	- ☐ Reusable with minor effort — small changes or clarifications needed
	- ☐ Reusable with significant effort — substantial cleanup/understanding required
	- ☐ Not reusable — tightly coupled to original setup or poorly documented
	- ☐ Not applicable — static data or fixed outputs only
- **Justification:** [Which results did you reproduce? Notes on tolerance]

## Detailed Evaluation

### Commands Executed
```bash
# Copy-paste the exact commands you ran
[command 1]
[command 2]
...
```

### Setup Process
[Describe the setup steps, any issues encountered, and time required]

### Testing Results
[What worked? What didn't? Any unexpected behavior?]

### Performance/Runtime
[Execution times, resource usage, scalability observations]

## Overall Assessment

**Reviewer expertise:**
- ☐ No familiarity — outside my area
- ☐ Some familiarity — basic knowledge; needed ramp up
- ☐ Knowledgeable — familiar with methods and tools
- ☐ Expert — deep expertise in this area

**Overall merit:**
- ☐ Strong accept — excellent artifact; sets a high standard
- ☐ Accept — solid quality; minor issues only
- ☐ Weak accept — generally positive; some concerns
- ☐ Weak reject — notable issues; could be improved
- ☐ Reject — insufficient quality or major gaps

## Comments for Authors

### Strengths
[What worked well? Positive aspects of the artifact]

### Issues and Suggestions
[Specific problems, missing components, unclear documentation, suggestions for improvement]

### Questions for Author Response
[Specific questions that could affect your evaluation]

## Comments for Program Committee
*(Hidden from authors)*

[Internal notes, confidential observations, comparison with other submissions]

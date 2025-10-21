---
order: 11
---

# Measuring security maturity

## Introduction

Measuring security maturity helps teams understand their current security posture and identify areas for improvement. Regular assessments support continuous improvement and help prioritise investment in training, tooling and secure development practices.

## Guidance

Teams **MUST**:

- conduct a security self-assessment every quarter
- assess their maturity using the following frameworks where appropriate:

  - [NIST Secure Software Development Framework (SSDF)][1]
  - [NCSC Cyber Assessment Framework (CAF)][2]
  - [Minimum Viable Secure Product (MVSP)][3]

  A RAG status **MUST** be recorded for each relevant standard or control. Statuses should be standardised where necessary in the following manner:

  - CAF defines specific criteria for `Red`, `Amber`, and `Green`
  - for MVSP, use:
    - `Red` = compliance gaps that must be addressed promptly
    - `Amber` = gaps that should be addressed but not urgently
    - `Green` = no or minor gaps
- review and refine these statuses with your assigned cybersecurity architect
- create an official risk for any red non-compliance
- track changes over time to identify trends and inform decisions

Assessment results **MAY** be used to:

- identify training needs
- prioritise security tooling or automation
- guide process improvements

## Measurement

| ID | Indicator | Green | Amber | Red |
| - | - | - | - | - |
| MSM-1 | Security self-assessments | Conducted in full quarterly | Conducted less frequently or not done in full | Not regular self-assessments |
| MSM-2 | Trends monitored over time | Used to inform improvements | Tracked but not used | Not tracked |

[1]: https://csrc.nist.gov/Projects/ssdf
[2]: https://www.ncsc.gov.uk/collection/caf
[3]: https://mvsp.dev

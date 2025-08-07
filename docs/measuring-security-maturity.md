# Measuring security maturity

## Introduction

Measuring security maturity helps teams understand their current security posture and identify areas for improvement. Regular assessments support continuous improvement and help prioritise investment in training, tooling and secure development practices.

## Guidance

Teams **MUST**:

- conduct a security self-assessment every quarter
- use the [NCSC CAF][1], and [MVSP][2] frameworks to assess their maturity
- record a RAG status for each relevant standard or control
  - CAF defines specific criteria for Red, Amber, and Green.
  - for MVSP, use Red = compliance gaps that must be addressed promptly, Amber = gaps that should be addressed but not urgently, Green = no or minor gaps.
- review and refine these statuses with your assigned cyber security architect
- create an official risk for any red non-compliances
- track changes over time to identify trends and inform decisions

Assessment results **MAY** be used to:

- identify training needs
- prioritise security tooling or automation
- guide process improvements

## Measurement

| ID    | Indicator                  | Green                       | Amber                                         | Red                          |
| ----- | -------------------------- | --------------------------- | --------------------------------------------- | ---------------------------- |
| MSM-1 | Security self-assessments  | Conducted in full quarterly | Conducted less frequently or not done in full | Not regular self-assessments |
| MSM-2 | Trends monitored over time | Used to inform improvements | Tracked but not used                          | Not tracked                  |

## References

- [NCSC Cyber Assessment Framework (CAF)][1]
- [Minimum Viable Secure Product (MVSP)][2]

[1]: https://www.ncsc.gov.uk/collection/caf
[2]: https://mvsp.dev

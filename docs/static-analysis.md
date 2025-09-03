---
order: 5
---

# Static analysis

## Introduction

Static analysis helps teams detect code quality and security issues early in the development process. It provides fast, automated feedback and reduces the risk of introducing defects into production.

Static analysis tools can be applied to application code, infrastructure as code and container configurations. They are most effective when integrated into CI/CD pipelines and run on every pull request. However, because pull request analysis is point-in-time, scheduled scans **SHOULD** also be used to detect newly disclosed vulnerabilities in previously committed code.

## Guidance

Teams **MUST**:

- run static analysis on every pull request and ensure all checks pass before merging
- use appropriate tools for the language or platform being used
- configure tools to enforce quality and security standards consistently

Teams **SHOULD**:

- schedule regular scans (e.g. daily or weekly) using tools such as **[Snyk][1]**, **[CodeQL][2]**, or platform-native scanners
- monitor scan results and triage new issues promptly

### Application code

For languages such as JavaScript, Python, Java and C#:

- [SonarQube][3] **MUST** be used to detect code quality issues
- [Snyk][1] **MUST** be used to detect known security vulnerabilities
- [Dependabot][4] **MUST** be used to identify and update outdated dependencies

### Infrastructure as code

For Terraform:

- [TFLint][5] **MUST** be used to detect code quality issues
- [Checkov][6] **MUST** be used to detect security misconfigurations
- [Infracost][7] **MUST** be used to estimate resource costs before deployment
- [Dependabot][4] **MUST** be used to keep Terraform modules up to date

### Containers

For container images:

- Image scanning **MUST** be performed using built-in tools such as [Amazon ECR scanning][8] or [Azure Container Registry (ACR)][9] with [Microsoft Defender for Cloud][10]

## Measurement

Use these indicators to assess adoption and effectiveness of static analysis practices.

| ID | Indicator | GREEN | AMBER | RED |
| - | - | - | - | - |
| SA-1 | Static analysis on pull requests | Run on **every pull request** with all checks passing | Run on some pull requests only | Not run or results ignored |
| SA-2 | Application code scanning | Tools configured and enforced for all supported languages | Tools used inconsistently or not enforced | Tools not used or misconfigured |
| SA-3 | Infrastructure as code scanning | Tools configured and enforced for Terraform | Tools used manually or partially | No scanning in place |
| SA-4 | Container image scanning | Automated scanning in CI/CD using approved tools | Manual scanning or partial coverage | No image scanning |
| SA-5 | Scheduled scanning | Regular scans configured and monitored | Scans configured but not monitored | No scheduled scanning |

## References

- [Amazon ECR image scanning][8]
- [Azure Container Registry image scanning][9]
- [Checkov][6]
- [CodeQL][2]
- [Dependabot][4]
- [Infracost][7]
- [Microsoft Defender for Containers][10]
- [Snyk][1]
- [SonarQube][3]
- [TFLint][5]

[1]: https://snyk.io
[2]: https://codeql.github.com
[3]: https://www.sonarsource.com/products/sonarqube
[4]: https://github.com/dependabot
[5]: https://github.com/terraform-linters/tflint
[6]: https://www.checkov.io
[7]: https://www.infracost.io
[8]: https://docs.aws.amazon.com/AmazonECR/latest/userguide/image-scanning.html
[9]: https://learn.microsoft.com/en-us/azure/container-registry/scan-images-defender
[10]: https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-containers-introduction

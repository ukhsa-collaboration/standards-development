---
order: 4
---

# Secure coding and tooling

## Introduction

Secure coding and automated tooling help teams build software that is safe, reliable and maintainable. By detecting issues early in the development process, teams can reduce the cost of remediation and improve delivery confidence.

This guidance sets out the minimum expectations for secure coding practices and the use of automated tools in engineering teams.

## Guidance

Teams **MUST**:

- use static analysis tools to detect code quality and security issues before merging code
- prevent secrets from being committed to source control (see [OWASP Secrets Management Cheat Sheet][6])
- perform Software Composition Analysis (SCA) to identify supply chain risks
- enforce security checks in CI/CD pipelines for all branches
- store secrets only in recommended secret managers (e.g. GitHub Actions Secrets, Azure Key Vault, AWS Secrets Manager)
- store non-secret but potentially sensitive data in recommended data stores (e.g. GitHub Actions, AWS Parameter Store, Azure App Configuration)

Teams **SHOULD**:

- use tools such as [SonarCloud][1], [Snyk][2], [CodeQL][3], and [detect-secrets][4] to automate scanning
- keep CI/CD jobs short and isolated to reduce feedback time
- run long-running scans asynchronously if they impact pipeline performance

Teams **MUST NOT**:

- merge code that fails static analysis or contains unresolved security issues
- store credentials, tokens, or other secrets in source control (including private repos)
- store configuration, IPs, resource IDs or similar meta data in source control (including private repos)
- rely on `.gitignore` or repo privacy for secret protection

## Secrets management

Secrets management is critical when using any source control system to store code and configuration.

Teams **SHOULD** align with the [OWASP Secrets Management Cheat Sheet][6] and **MUST** follow these minimum practices:

- **Detect**: enable secret scanning and pre-commit hooks to stop secrets entering git history.
- **Remove**: scrub any historical secrets before committing.
- **Store securely**: use GitHub Actions Secrets, or an external secret manager (AWS Secrets Manager, Azure Key Vault).
- **Rotate**: change secrets immediately if exposed or compromised. Prefer short-lived or dynamic secrets where possible. For long-lived static secrets, set a risk-based maximum age until rotation can be automated.
- **Automate**: avoid manual sharing; inject secrets into pipelines or runtimes only when needed.

A secret is anything that grants access (credentials, tokens, keys, connection strings). Identifiers and metadata (e.g. IPs, ARNs, resource IDs, file paths) are not secrets, but may still be sensitive and useful to an attacker. Non-secret, but sensitive data should be handled carefully. Avoid hard-coding, minimise exposure in logs, and where practical store them in a parameter/configuration service (e.g. AWS Systems Manager Parameter Store, Azure App Configuration/Key Vault). 

> [!TIP]
> If in doubt, treat the data as a secret.

## Recommended tools

The tools listed below help teams automate secure coding practices and reduce manual effort. They support early detection of issues, improve consistency across projects, and integrate easily into CI/CD workflows.

Teams **SHOULD** choose tools that suit their technology stack and delivery context, and **MUST** ensure they are properly configured and maintained.

| Area | Tool | Purpose |
| - | - | - |
| Code quality | [SonarQube][1] | Detects bugs, code smells and vulnerabilities |
| Dependency management | [Dependabot][5] | Automates updates to vulnerable dependencies |
| Secrets detection | [detect-secrets][4] | Prevents secrets from being committed |
| Security scanning | [CodeQL][3] | Performs semantic code analysis to detect security vulnerabilities |
| Security scanning | [Snyk][2] | Identifies known vulnerabilities in dependencies |

## Measurement

Use these indicators to assess adoption and effectiveness of secure coding and tooling practices.

| ID | Indicator | GREEN | AMBER | RED |
| - | - | - | - | - |
| SCT-1 | Static analysis in CI/CD | Enforced on **all branches** with blocking checks | Enforced on **main** branch only | Not enforced or bypassable |
| SCT-2 | SCA reports reviewed | Reviewed **regularly** with actions tracked in backlog | Reviewed **occasionally** or inconsistently | Not reviewed or no evidence |
| SCT-3 | Secrets management | No secrets in source control; scanning tools in place and effective | Secrets removed after detection; no scanning tools in place | Secrets present in code or committed by team |
| SCT-4 | Tooling coverage | All relevant tools integrated and actively used in CI/CD | Some tools integrated or used manually | No tooling or ad hoc usage |
| SCT-5 | Developer awareness | All developers trained on secure coding and tooling practices | Some developers trained or training outdated | No training or awareness activity |

## References

- [CodeQL][3]
- [Dependabot][5]
- [detect-secrets][4]
- [Snyk][2]
- [SonarQube][1]
- [OWASP Secrets Management Cheat Sheet][6]

[1]: https://www.sonarsource.com/products/sonarqube
[2]: https://snyk.io
[3]: https://codeql.github.com
[4]: https://github.com/Yelp/detect-secrets
[5]: https://github.com/dependabot
[6]: https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html

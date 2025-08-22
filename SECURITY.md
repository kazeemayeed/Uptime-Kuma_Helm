# Security Policy

## Supported Versions

We actively maintain and support the **latest release** only.  
Please ensure you're using the most recent version to benefit from the latest security fixes.

| Version         | Supported |
|-----------------|-----------|
| Latest release  |  Yes    |
| Older versions  |  No     |

---

## Reporting a Vulnerability

If you discover a security issue, please **do not open a public GitHub issue**.  
Instead, report it responsibly:

1. git checkout -b feature/<short-description>
# or
git checkout -b fix/<short-description> 

2. **Do not** share exploit details publicly until the issue is resolved.  

3. We will acknowledge your report within **48 hours** and provide a timeline for remediation.

---

## Disclosure Policy

We follow a **responsible disclosure** approach:

- Security issues are handled **privately** until resolved.
- Once a fix is available, a public advisory will be published—unless anonymity is requested.
- Please allow reasonable time for resolution before publicly disclosing the issue.

---

## Security Recommendations for Users

For a secure deployment, consider the following best practices:

- Always install the **latest release** of the chart.
- Use only **pinned container image tags**—avoid using `latest` or floating tags.
- Configure resource **requests and limits** (CPU and memory) in your `values.yaml`.
- Enable **readiness** and **liveness probes** for the Uptime-Kuma pods.
- Avoid deploying naked pods—ensure you use Deployments, StatefulSets, or similar controllers.
- Do not commit secrets (like admin credentials) into the repo—use Kubernetes Secrets instead.
- Enable GitHub security features like Dependabot, code scanning, and security alerts for proactive protection.
- Regularly scan your deployment with vulnerability scanners (e.g., Trivy, Clair) and compliance tools (e.g., Checkov).

---

## Acknowledgments

Thank you for helping keep **Uptime-Kuma_Helm** secure and trusted for the community!


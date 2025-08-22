# Contributing to Uptime-Kuma Helm

First off, thanks for taking the time to contribute!
This project thrives because of contributions from people like you.

---

## How Can I Contribute?

### Reporting Issues
- Check existing issues to avoid duplicates.
- Provide clear steps to reproduce the problem.
- Include details about your environment (Kubernetes version, Helm version, etc.).

### Suggesting Enhancements
- Open an issue to discuss your idea before submitting a PR.
- Describe why the enhancement is useful and how it improves the chart.

### Pull Requests
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/my-feature`).
3. Make your changes.
4. Run linting/tests (see below).
5. Commit using clear messages.
6. Push your branch and open a Pull Request against `main`.

---

## Development Guidelines

- **YAML Formatting**: Use 2 spaces for indentation.
- **Helm Best Practices**: Follow [Helm chart guidelines](https://helm.sh/docs/chart_best_practices/).
- **Keep Values Flexible**: All configurable parameters should be defined in `values.yaml`.
- **Secrets**: Do not commit secrets. Use placeholders instead.

---

## Testing

Before opening a PR:
- Run Helm lint:
  ```bash
  helm lint .

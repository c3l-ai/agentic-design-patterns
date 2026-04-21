# Security Policy

## Scope

This repository contains the source for an open academic book rendered as a static website. It does not include executable application code, user authentication, databases, or data collection.

The primary security considerations for this project are:

- **Content integrity** — ensuring the published text accurately reflects the authors' work and has not been tampered with.
- **Dependency vulnerabilities** — the Quarto build system and GitHub Actions workflow have dependencies that may contain vulnerabilities.
- **Malicious pull requests** — contributions that attempt to inject harmful content into the published site.

## Reporting a vulnerability

If you discover a security issue related to this repository — including a compromised dependency in the build pipeline, a vulnerability in the GitHub Actions workflow, or any attempt to inject harmful content — please report it privately rather than opening a public issue.

**Contact:** Open a [private security advisory](https://github.com/c3l-ai/agentic-design-patterns/security/advisories/new) via GitHub's security reporting feature.

Please include:

- A description of the issue and its potential impact
- Steps to reproduce or demonstrate the vulnerability
- Any suggested remediation if you have one

We will acknowledge receipt within 5 business days and aim to resolve confirmed issues within 30 days.

## Supported versions

This project is actively maintained. Security issues will be addressed in the current version only.

## Dependencies

The build pipeline uses:

- [Quarto](https://quarto.org) — for rendering the book
- GitHub Actions — for deployment to GitHub Pages
- Google Fonts — loaded at render time for typography

If you discover a vulnerability in any of these dependencies that affects this project, please report it both to us and to the upstream maintainer.

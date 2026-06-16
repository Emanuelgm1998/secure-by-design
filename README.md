
<div align="center">

<img src="https://img.shields.io/badge/status-live-22c55e?style=flat-square" />
&nbsp;
<img src="https://img.shields.io/github/actions/workflow/status/Emanuelgm1998/secure-by-design/pages.yml?branch=main&label=deploy&style=flat-square&logo=github-actions&logoColor=white" />
&nbsp;
<img src="https://img.shields.io/badge/HTTPS-enforced-38bdf8?style=flat-square&logo=letsencrypt&logoColor=white" />


# secure-by-design

**Cloud Security & DevSecOps Engineering Portfolio**

*Zero Trust · AWS-first · Terraform IaC · GitOps*

<br/>

**[→ emanuelgm1998.github.io/secure-by-design](https://emanuelgm1998.github.io/secure-by-design/)**

</div>

---

## Overview

Public portfolio for **Emanuel G. Michea** — Cloud Security & DevSecOps Engineer based in Santiago, Chile.

The site itself reflects the same engineering principles applied to production infrastructure: no frameworks, no build step, no runtime dependencies. A single `index.html` deployed via GitHub Actions to GitHub Pages — HTTPS enforced, globally cached, zero maintenance overhead.

> A portfolio for a security engineer should have the smallest possible attack surface. Zero dependencies means zero supply chain risk.

---

## Architecture

```
Developer                  GitHub                        CDN
    │                         │                           │
    ├── git push ─────────────►│                           │
    │                         │                           │
    │                  ┌──────▼──────────────────────┐    │
    │                  │       GitHub Actions          │    │
    │                  │                              │    │
    │                  │  1. actions/checkout@v4      │    │
    │                  │  2. actions/configure-pages@v5│   │
    │                  │  3. actions/upload-pages-     │    │
    │                  │     artifact@v3               │    │
    │                  │  4. actions/deploy-pages@v4  │    │
    │                  └──────────────┬───────────────┘    │
    │                                 │                    │
    │                                 ▼                    │
    │                  ┌──────────────────────────────┐    │
    │                  │       GitHub Pages            │    │
    │                  │   HTTPS · Global edge cache  ├───►│
    │                  │   emanuelgm1998.github.io/   │    │
    │                  │      secure-by-design/        │    │
    │                  └──────────────────────────────┘    │
```

| Property | Value |
|---|---|
| Trigger | Every push to `main` |
| Deploy time | ~25 seconds |
| Downtime | Zero — atomic swap via Pages CDN |
| Dependencies | Zero |

---

## Security decisions

```yaml
# .github/workflows/pages.yml
on:
  push:
    branches: [ "main" ]

permissions:
  contents: read
  pages: write
  id-token: write        # OIDC — no static deploy tokens
```

Every permission is explicitly scoped:

- `contents: read` — runner cannot write back to the repo
- `id-token: write` — OIDC federation, no long-lived secrets stored anywhere
- No third-party actions beyond the official `actions/*` org — full supply chain control

---

## Stack

| Layer | Choice | Rationale |
|---|---|---|
| Markup | HTML5 semantic | Accessibility, SEO, zero transpilation |
| Style | CSS custom properties | Zero runtime, design tokens in one place |
| Fonts | Google Fonts (IBM Plex Mono · Inter · Syne) | Async load, no render blocking |
| Deploy | GitHub Actions → Pages | Native OIDC, no external CI dependency |
| TLS | GitHub Pages (Let's Encrypt) | Automatic renewal, HSTS enforced |
| Dependencies | **Zero** | No npm, no bundler, no attack surface |

---

## Site sections

| Section | Content |
|---|---|
| Hero | Name, title, bio, CTAs |
| AWS Focus | ECS Fargate, VPC, IAM, Secrets Manager, CloudWatch, Well-Architected |
| Core Skills | IAM Zero Trust · Terraform IaC · DevSecOps pipelines · Container security · Observability · Supply chain |
| Projects | AWS DevSecOps Infrastructure Platform |
| Certifications | Linux Foundation (6) · Cisco (3) |
| Contact | Email · LinkedIn · GitHub |

---

## Featured project

**[aws-devsecops-infrastructure](https://github.com/Emanuelgm1998/aws-devsecops-infrastructure)**

Production-oriented multi-AZ AWS platform — ECS Fargate behind ALB, modular Terraform, GitHub Actions GitOps pipeline, IAM Least Privilege per service, Secrets Manager with KMS, CloudWatch SLI/SLO dashboards. Ephemeral deployment cost: ~$0.02 per cycle.

---

## Local preview

```bash
# No install required
open index.html

# Or serve locally
python3 -m http.server 8080
# → http://localhost:8080
```

---

## Engineer

**Emanuel G. Michea**
Cloud Security & DevSecOps Engineer · Santiago, Chile

[![Portfolio](https://img.shields.io/badge/Portfolio-secure--by--design-0f172a?style=flat-square&logo=github)](https://emanuelgm1998.github.io/secure-by-design/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Emanuel%20G.%20Michea-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/emanuelgm1998)
[![GitHub](https://img.shields.io/badge/GitHub-Emanuelgm1998-181717?style=flat-square&logo=github)](https://github.com/Emanuelgm1998)

> *Building infrastructure that is secure by design, not by accident.*


**Emanuel G. Michea**
Cloud Security & DevSecOps Engineer · Santiago, Chile



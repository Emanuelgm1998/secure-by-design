<div align="center">

<img src="https://img.shields.io/badge/status-live-22c55e?style=flat-square" />
&nbsp;
<img src="https://img.shields.io/github/actions/workflow/status/Emanuelgm1998/secure-by-design/pages.yml?branch=main&label=deploy&style=flat-square&logo=github-actions&logoColor=white" />
&nbsp;
<img src="https://img.shields.io/badge/HTTPS-enforced-38bdf8?style=flat-square&logo=letsencrypt&logoColor=white" />
&nbsp;
<img src="https://img.shields.io/github/last-commit/Emanuelgm1998/secure-by-design?style=flat-square&color=64748b" />

<br/><br/>

# secure-by-design

**Cloud Security & DevSecOps Engineering Portfolio**

*Zero Trust · AWS-first · Terraform IaC · GitOps*

<br/>

**[→ emanuelgm1998.github.io/secure-by-design](https://emanuelgm1998.github.io/secure-by-design/)**

</div>

---

## What this is

Public portfolio for **Emanuel G. Michea** — Cloud Security & DevSecOps Engineer based in Santiago, Chile.

The site itself is engineered, not just designed: no frameworks, no build step, no runtime dependencies. A single `index.html` deployed via GitHub Actions to GitHub Pages — HTTPS enforced, globally cached, zero maintenance overhead.

> The stack choice is intentional. A portfolio for a security engineer should have the smallest possible attack surface.

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

**Trigger:** every push to `main`
**Deploy time:** ~25 seconds
**Downtime:** zero — atomic swap via Pages CDN

---

## Workflow

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

Security decisions in the workflow:
- `contents: read` — runner cannot write back to the repo
- `id-token: write` — uses OIDC federation, no long-lived secrets stored
- No third-party actions beyond official `actions/*` org

---

## Stack

| Layer | Choice | Rationale |
|---|---|---|
| Markup | HTML5 semantic | Screen readers, SEO, no transpilation |
| Style | CSS custom properties | Zero runtime, theme tokens in one place |
| Fonts | Google Fonts (IBM Plex Mono · Inter · Syne) | Loaded async, no render block |
| Deploy | GitHub Actions → Pages | Native OIDC, no external CI dependency |
| TLS | GitHub Pages (Let's Encrypt) | Automatic renewal, HSTS enforced |
| Dependencies | **Zero** | No npm, no bundler, no attack surface |

---

## Site sections

| Section | Purpose |
|---|---|
| Hero | Name, title, bio, CTA — view projects / LinkedIn / CV download |
| AWS Focus | Primary specialization: ECS Fargate, VPC, IAM, Secrets Manager, CloudWatch |
| Core Skills | IAM Zero Trust · Terraform IaC · DevSecOps pipelines · Container security · Observability · Supply chain |
| Projects | AWS DevSecOps Infrastructure Platform · Zero Trust Framework · Kubernetes Security Lab |
| Certifications | Linux Foundation (6) · Cisco (3) |
| Contact | Email · LinkedIn · GitHub · CV (PDF download) |

---

## Featured project

**[aws-devsecops-infrastructure](https://github.com/Emanuelgm1998/aws-devsecops-infrastructure)**
Production-grade multi-AZ AWS platform — ECS Fargate, modular Terraform, GitHub Actions GitOps, IAM Least Privilege, Secrets Manager, CloudWatch SLI/SLO. ~$0.02 per ephemeral deployment cycle.

---

## Local preview

```bash
# No install required — open directly
open index.html

# Or serve locally
python3 -m http.server 8080
# → http://localhost:8080
```

---

## Engineer

**Emanuel G. Michea**
Cloud Security & DevSecOps Engineer · Santiago, Chile

[![Portfolio](https://img.shields.io/badge/Portfolio-secure--by--design-0f172a?style=flat-square&logo=github)](https://emanuelgm1998.github.io/secure-by-design/) mejora el readme mejoral

🔗 Portfolio: [https://emanuelgm1998.github.io/secure-by-design](https://emanuelgm1998.github.io/secure-by-design)
🔗 GitHub: [https://github.com/Emanuelgm1998](https://github.com/Emanuelgm1998)
🔗 LinkedIn:  [https://www.linkedin.com/in/emanuel-gonzalez-michea/)

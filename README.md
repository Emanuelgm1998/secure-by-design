Aquí tienes el **README completo listo para copiar y pegar** en GitHub Pages / repo sin que tengas que tocar nada más:

```md
# 🔐 secure-by-design

<div align="center">

<img src="https://img.shields.io/badge/status-live-22c55e?style=flat-square" />
&nbsp;
<img src="https://img.shields.io/github/actions/workflow/status/Emanuelgm1998/secure-by-design/pages.yml?branch=main&label=deploy&style=flat-square&logo=github-actions&logoColor=white" />
&nbsp;
<img src="https://img.shields.io/badge/HTTPS-enforced-38bdf8?style=flat-square&logo=letsencrypt&logoColor=white" />
&nbsp;
<img src="https://img.shields.io/github/last-commit/Emanuelgm1998/secure-by-design?style=flat-square&color=64748b" />

<br/><br/>

**Cloud Security & DevSecOps Engineering Portfolio**

Zero Trust · AWS-first · Terraform IaC · GitOps · Secure by Design

<br/>

🔗 https://emanuelgm1998.github.io/secure-by-design/

</div>

---

## 📌 Overview

Portfolio profesional de **Emanuel G. Michea** — Cloud Security & DevSecOps Engineer (Santiago, Chile).

Este proyecto no es solo un sitio web: es una demostración de ingeniería enfocada en seguridad, minimalismo y reducción de superficie de ataque.

- Sin frameworks
- Sin build step
- Sin dependencias externas
- Sin runtime innecesario

👉 Solo HTML + CSS + GitHub Actions + GitHub Pages

> Diseño intencional: menos complejidad = menos superficie de ataque.

---

## 🧠 Architecture (Secure-by-Design)

```

Developer → GitHub → GitHub Actions → GitHub Pages (CDN)

````

### Flow de despliegue

- Push a `main`
- GitHub Actions ejecuta pipeline
- Artifact generado y desplegado a Pages
- CDN global con TLS automático (Let’s Encrypt)

### Características clave

- 🔐 Deploy sin secretos (OIDC)
- ⚡ Deploy atómico (~25s)
- 🌍 Edge caching global
- 🚫 Cero downtime

---

## ⚙️ CI/CD Pipeline (GitHub Actions)

```yaml
on:
  push:
    branches: ["main"]

permissions:
  contents: read
  pages: write
  id-token: write  # OIDC authentication (no static tokens)
````

### Seguridad aplicada

* ❌ Sin PATs (Personal Access Tokens)
* ❌ Sin secretos hardcodeados
* ✅ OIDC federation
* ✅ Permisos mínimos (least privilege)
* ✅ Solo actions oficiales (`actions/*`)

---

## 🧱 Tech Stack

| Layer   | Technology                   | Rationale                      |
| ------- | ---------------------------- | ------------------------------ |
| UI      | HTML5 semantic               | Accesible + SEO + zero tooling |
| Styling | CSS variables                | Theming sin runtime            |
| Fonts   | Inter · IBM Plex Mono · Syne | Performance + legibilidad      |
| CI/CD   | GitHub Actions               | Native + OIDC                  |
| Hosting | GitHub Pages                 | TLS + CDN global               |
| Infra   | Zero dependencies            | Reduced attack surface         |

---

## 🧩 Key Features

* 🔐 Zero Trust mindset aplicado a frontend deployment
* 🚀 GitOps workflow con GitHub Actions
* 🌐 HTTPS enforcement automático
* 📦 Deploy sin build system (no Node, no npm)
* 📊 Arquitectura reproducible y audit-friendly

---

## 📂 Site Structure

| Section        | Description                                       |
| -------------- | ------------------------------------------------- |
| Hero           | Branding personal + CTA                           |
| Cloud Security | AWS, IAM, Zero Trust, DevSecOps                   |
| Skills         | Terraform · Kubernetes · Observability · Security |
| Projects       | Infra AWS + Security Labs                         |
| Certifications | Linux Foundation · Cisco                          |
| Contact        | LinkedIn · GitHub · CV                            |

---

## 🚀 Featured Project

### 🔗 AWS DevSecOps Infrastructure Platform

[https://github.com/Emanuelgm1998/aws-devsecops-infrastructure](https://github.com/Emanuelgm1998/aws-devsecops-infrastructure)

Plataforma cloud production-ready con enfoque en seguridad:

* AWS ECS Fargate
* Terraform modular (IaC)
* IAM least privilege
* Secrets Manager
* CloudWatch observability
* GitHub Actions GitOps
* Cost optimization (~$0.02 per deploy cycle)

---

## 💻 Local Development

```bash
python3 -m http.server 8080
```

Abrir:

```
http://localhost:8080
```

---

## 🧭 Engineering Philosophy

* Security by default, not by add-on
* Minimal attack surface over complexity
* Infrastructure as Code > manual configuration
* Reproducibility over abstraction
* Transparency over black-box systems

---

## 👤 Author

**Emanuel G. Michea**
Cloud Security & DevSecOps Engineer — Santiago, Chile

🔗 Portfolio: [https://emanuelgm1998.github.io/secure-by-design](https://emanuelgm1998.github.io/secure-by-design)
🔗 GitHub: [https://github.com/Emanuelgm1998](https://github.com/Emanuelgm1998)
🔗 LinkedIn:  [https://www.linkedin.com/in/emanuel-gonzalez-michea/)

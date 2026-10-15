# Documentation Content

This repository contains documentation for multiple projects. You can build and view them locally using Sphinx.

## Projects

- [Admin Portal]
- [Backup As A Service](ABAS/source/index)
- [Partner Portal]
- [Paystack](Paystack/source/index)
- [Zoho](Zoho/source/index)

## 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/your-org/software-docs.git
cd software-docs
```

Install dependencies:

```bash
poetry install
```

Run the documentations locally:

```bash
poetry run sphinx-autobuild . build/html
```

open in your browser: http://127.0.0.1:8000



## 📦 Deployment

To build static HTML for deployment:

```bash
poetry run sphinx-build -b html . build/html
```

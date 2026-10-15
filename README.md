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

Upload the contents of build/html to your hosting platform (e.g., GitHub Pages, Netlify, or an Nginx server).


## 📝 Guidelines for Creating Individual Documentation Projects

Each project (e.g., Paystack, Zoho, ABAS, Admin Portal, Partner Portal) should have its own Sphinx setup. Follow these steps:

1. Create a project folder
2. Initialize a new Sphinx project within the folder

    ```bash
    poetry run sphinx-quickstart
    ```
   
    or

    ```bash
    sphinx-quickstart
    ```

This generates `conf.py` and other necessary files.

3. Configure the Sphinx project according to your needs
4. Add content to the project
5. Build the documentation using Sphinx

    ```bash
    poetry run sphinx-autobuild source build/html
    ```

6. Link to the master project and add reference to each subproject.

    ```bash
   .. toctree::
   :maxdepth: 2
   :caption: Projects:

   ABAS/source/index
   Paystack/source/index
   Zoho/source/index
   AdminPortal/source/index
   PartnerPortal/source/index

    ```

7. Keep styles consistent.
Use the same theme (e.g., sphinx_rtd_theme) and extensions across all subprojects so the unified docs look seamless.
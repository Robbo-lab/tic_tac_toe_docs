# Project Documentation with Sphinx and sphinx_rtd_theme

This guide helps you set up and manage documentation for your Python project using **Sphinx** and the **Read the Docs theme (`sphinx_rtd_theme`)** via the command line.

---

## Prerequisites

Make sure you have Python and pip installed.

Install Sphinx and the Read the Docs theme:

```bash
pip install sphinx sphinx_rtd_theme
```

---

### 1. Create a `docs/` directory

```bash
mkdir docs
cd docs
```

### 2. Initialize Sphinx

```bash
sphinx-quickstart
```

Answer the prompts (you can accept the defaults or customize as needed). This will create a bunch of files including `conf.py`.

---

## Configure the Theme

Open `docs/conf.py` and modify or add the following lines:

```python
import os
import sys
sys.path.insert(0, os.path.abspath('..'))

# Use the Read the Docs theme
html_theme = 'sphinx_rtd_theme'

# Optional: if using custom static files
# html_static_path = ['_static']
```

---

## Document Your Project

Make sure your Python modules are accessible and include docstrings.

To automatically generate `.rst` files for your Python code:

```bash
sphinx-apidoc -o source/ ../your_package_name
```

Replace `your_package_name` with the directory name of your Python package.

---

## Build the Documentation

To generate the HTML documentation:

```bash
make html
sphinx-build -M html docs/ _build/
```

Your documentation will be built in `docs/build/html/index.html`.

To view it locally:

```bash
open build/html/index.html  # macOS
# or
xdg-open build/html/index.html  # Linux
# or
start build/html/index.html  # Windows
```

---

## Useful CLI Commands

| Command                             | Description                                 |
|-------------------------------------|---------------------------------------------|
| `sphinx-quickstart`                 | Start a new Sphinx documentation project    |
| `sphinx-apidoc -o source/ ../pkg`  | Generate .rst files from your Python code   |
| `make html`                         | Build the HTML version of the docs          |
| `make latexpdf`                     | Build PDF documentation (requires LaTeX)    |
| `make clean`                        | Remove previously built docs                |

---

```txt
# requirements.txt
sphinx
sphinx_rtd_theme
```

---

## Example Directory Structure

```
your_project/
├── your_package/
│   └── __init__.py
├── docs/
│   ├── build/
│   ├── source/
│   │   ├── conf.py
│   │   ├── index.rst
│   │   └── your_package.rst
│   └── Makefile
└── README.md
```

---

## 🧠 Tips

- Use reStructuredText or Markdown (with extensions) for your content.
- Keep your `index.rst` organized and include a `toctree` directive.
- Run `make clean html` if changes don’t show up.

---

Happy documenting! 🖊️📄
```

---

Let me know if you’d like a version using Markdown files with `MyST` instead of `.rst`, or to include instructions for PDF/LaTeX output too!

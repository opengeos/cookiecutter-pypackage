# Cookiecutter PyPackage

[![image](https://github.com/opengeos/cookiecutter-pypackage/workflows/build/badge.svg)](https://github.com/opengeos/cookiecutter-pypackage/actions?query=workflow%3Abuild)
[![image](https://github.com/opengeos/cookiecutter-pypackage/workflows/docs/badge.svg)](https://open.gishub.org/cookiecutter-pypackage)

[Cookiecutter](https://github.com/cookiecutter/cookiecutter) template for a Python package.

-   GitHub repo: <https://github.com/opengeos/cookiecutter-pypackage>
-   Documentation: <https://open.gishub.org/cookiecutter-pypackage>
-   Free software: BSD license

## Features

-   Testing setup with `unittest` and `python setup.py test` or `pytest`
-   GitHub actions: Ready for GitHub Continuous Integration testing
-   [bump2version](https://github.com/c4urself/bump2version): Pre-configured version bumping with a single command
-   Auto-release to [PyPI](https://pypi.python.org/pypi) when you push a new tag to master (optional)
-   Command line interface using Click (optional)

## Usage

This guide provides detailed steps on how to create a Python package, configure it for distribution, and manage its versioning and releases. First, install `cookiecutter` and `bump-my-version` and then follow the steps below.

```bash
pip install cookiecutter bump-my-version
```

### 1. Create the Package Structure

Use `cookiecutter` to create a package structure. `cookiecutter` is a command-line utility that creates projects from templates.

```bash
cookiecutter gh:opengeos/cookiecutter-pypackage
```

### 2. Initialize and Commit to Git

Navigate to your project directory and initialize a Git repository:

```bash
cd your-package-name
git init
git add .
git commit -m "Initial commit"
```

### 3. Create a Repository on GitHub

-   Go to [GitHub](https://github.com/) and create a new empty repository.
-   Do NOT initialize it with a README, license, or .gitignore file.

### 4. Add Git Remote

Link your local repository to the GitHub repository. If your git branch is named `main`, use the following commands:

```bash
git remote add origin [your-repository-url]
git branch -M main
git push -u origin main
```

If your git branch is named `master`, use the following commands:

```bash
git remote add origin [your-repository-url]
git branch -M master
git push -u origin master
```

### 5. Configure GitHub Actions

Change the GitHub Actions settings in your repository to allow read and write operations:

-   Go to your repository on GitHub.
-   Click on `Settings` > `Actions` > `General` > `Workflow permissions`.
-   Change the settings to allow **read and write operations**.

### 6. Push to GitHub

Push your local changes to GitHub:

```bash
git push
```

### 7. Create an API Token on PyPI

-   Visit [pypi.org](https://pypi.org) and log in or create an account.
-   Navigate to `Account Settings` > `API Tokens`.
-   Create a new API token. Select `Entire account` as the scope. Copy the token.

### 8. Add GitHub Repository Secrets

Add your PyPI credentials as secrets in your GitHub repository:

-   Go to your repository on GitHub.
-   Click on `Settings` > `Secrets` > `New repository secret`.
-   Add `PYPI_USERNAME` as a secret. Use `__token__` as the value.
-   Add `PYPI_PASSWORD` as a secret. Use the API token created above as the password.

### 9. Make a Release on GitHub

Create a release on GitHub to trigger the deployment of your package:

-   Go to the `Releases` section in your GitHub repository.
-   Click `Draft a new release`.
-   Follow the prompts to create the release.

### 10. Enable GitHub Pages

-   Navigate to `Settings` > `Pages`.
-   Select the `gh-pages` branch as the source.
-   Click `Save`.

### 11. Version Management with bump-my-version

Use `bump-my-version` for managing the version of your package:

-   First, do a dry run to see what changes will be made:

```bash
bump-my-version bump [patch/minor/major] --dry-run --verbose
```

-   If satisfied, apply the version bump:

```bash
bump-my-version bump [patch/minor/major]
```

### 12. Push Tags and Changes to GitHub

After bumping the version, push the tags and changes:

```bash
git push --tags
git push
```

### 13. Make a New Release on GitHub

Finally, make a new release on GitHub with the updated version:

-   Repeat the process described in step 9.

---

Remember to replace placeholders (like `your-package-name` and `[your-repository-url]`) with actual values relevant to your package. This guide assumes basic familiarity with Git, GitHub, and Python packaging conventions.

## Video Tutorials

**1. Creating a Python package with Cookiecutter Template**

[![](http://img.youtube.com/vi/DAPAv9KbYZ0/0.jpg)](http://www.youtube.com/watch?v=DAPAv9KbYZ0)

**2. Publishing Python packages on PyPI**

[![](http://img.youtube.com/vi/7FcX9uWDuIQ/0.jpg)](http://www.youtube.com/watch?v=7FcX9uWDuIQ)

**3. Deploying Python packages to PyPI using GitHub Actions**

[![](http://img.youtube.com/vi/oayticDOZmU/0.jpg)](http://www.youtube.com/watch?v=oayticDOZmU)

**4. Introduction to Python package file structure**

[![](http://img.youtube.com/vi/0eLt_O6sIYU/0.jpg)](http://www.youtube.com/watch?v=0eLt_O6sIYU)

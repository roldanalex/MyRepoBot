# Automate Github Repository

**Streamline your workflow by automating the creation of Github repositories and R project templates directly from the command line.**

## Overview

This tool simplifies the process of initializing new projects. Whether you are setting up a standard Github repository or a specialized R project template, this automation script handles both the local directory creation and the remote Github repository setup.

## Key Benefits

*   **Efficiency**: Create local and remote repositories in a single step.
*   **Standardization**: Easily deploy R project templates to ensure consistent project structure (includes folders for app, data, figs, docs, src, report).
*   **Automation**: Eliminate manual setup steps on Github.com.
*   **CLI Integration**: Designed for seamless integration into your terminal workflow.

## Prerequisites

Before running the application, ensure you have the following:

1.  **Python 3**: Ensure Python 3 is installed.
2.  **Github Account**: You need a Github account and a Personal Access Token.

## Installation

1.  Clone this repository to your local machine.
2.  Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

## Configuration

You must create a configuration file named `Git_Token.py` in the same directory as the scripts. This file stores your credentials and preferences.

1.  Create a file named `Git_Token.py`.
2.  Add the following variables to the file:

    ```python
    # Git_Token.py
    TOKEN = "YOUR_GITHUB_PERSONAL_ACCESS_TOKEN"
    REPOSITORY_PATH = "/path/to/your/local/projects/"
    GITHUB_USER = "your_github_username"
    ```

    *   `TOKEN`: Your Github Personal Access Token (ensure it has `repo` scope).
    *   `REPOSITORY_PATH`: The absolute path to the folder where you want your local projects created.
    *   `GITHUB_USER`: Your Github username.

## Usage

### Create a Standard Github Repository

To create a standard repository with a README:

```bash
python3 create_git_repo.py --name <repo_name> [--private]
```

*   **Example**: `python3 create_git_repo.py --name my-new-project --private`

### Create an R Project Template

To create a repository with a specific folder structure for R Shiny apps or analysis projects:

```bash
python3 create_r_project.py --name <project_name> [--private]
```

**Structure Created:**
*   **Folders**: `app` (with `www`, `rds`, `utils`), `data`, `figs`, `docs`, `src`, `report`.
*   **Files**: `ui.R`, `server.R`, `global.R`.
*   **Git**: Initializes repo, adds `.gitignore` configured for R, and pushes to Github.

## Preview

<img src="figs/Github_Auto_R.png" alt="R Project Example">
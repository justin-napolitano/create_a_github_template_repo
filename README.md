# create_a_github_template_repo

This repository demonstrates how to leverage GitHub template repositories to automate the deployment of common scripts across multiple projects. It provides a practical example of using a template to ensure consistent inclusion of a synchronization script in new repositories.

## Features

- Automates the inclusion of shared scripts in new repositories via GitHub templates
- Uses GitHub CLI commands to manage template repositories
- Streamlines repository setup and standardizes project scaffolding

## Tech Stack

- GitHub Repositories
- GitHub CLI (gh)
- Shell scripting (assumed for `gh_submodule_sync.sh` script)

## Getting Started

### Prerequisites

- Install [GitHub CLI](https://cli.github.com/)
- Have an existing repository with the desired scripts (e.g., `gh_submodule_sync`)

### Setup

1. Clone your existing repository intended as a template:

   ```sh
   git clone https://github.com/justin-napolitano/gh_submodule_sync.git
   cd gh_submodule_sync
   ```

2. Mark the repository as a template:

   ```sh
   gh api -X PATCH /repos/justin-napolitano/gh_submodule_sync -f is_template=true
   ```

3. Create a new repository from the template:

   ```sh
   gh repo create new-repo --template=justin-napolitano/gh_submodule_sync --public --confirm
   ```

4. Clone the newly created repository:

   ```sh
   git clone https://github.com/justin-napolitano/new-repo.git
   cd new-repo
   ```

## Project Structure

- `index.md`: Documentation explaining the process and rationale for using GitHub template repositories to automate script deployment.

## Future Work / Roadmap

- Add automation scripts to update existing repositories with the latest template changes
- Provide examples of integrating additional common scripts or configurations
- Include CI/CD pipeline templates for streamlined project setup
- Expand documentation with troubleshooting and advanced usage scenarios

---

*Note: This repository currently serves as documentation and an example setup. The actual synchronization script (`gh_submodule_sync.sh`) resides in the referenced template repository.*
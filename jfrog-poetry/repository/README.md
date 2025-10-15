# Connecting to a Private PyPI Repository via JFrog Artifactory

This guide helps you securely configure [Poetry](https://python-poetry.org/) to use a private PyPI repository hosted on JFrog Artifactory.

## Prerequisites

- [Poetry](https://python-poetry.org/docs/#installation) installed
- Access to your JFrog Artifactory PyPI repository
- Credentials (username and password or API key)

---

## Step 1: Add Your Repository

Choose a local name (e.g., `company-pypi`) and add your repository:

```sh
poetry config repositories.<local-name> https://gwproductengineering.jfrog.io/artifactory/api/pypi/acuity-core-pypi-prod
```

## Step 2: Configure Authentication

Set up HTTP basic authentication. Replace `<username>` and `<password>` with your credentials:

```sh
poetry config http-basic.<local-name> $POETRY_REPO_USER $POETRY_REPO_PASS
```

> **Security Tip:**  
> Use environment variables to avoid exposing credentials:
>
> ```sh
> poetry config http-basic.<local-name> $POETRY_REPO_USER $POETRY_REPO_PASS
> ```

## Step 3: Add the Repository as a Source

Register the repository as a source for Poetry:

```sh
poetry source add <local-name> https://gwproductengineering.jfrog.io/artifactory/api/pypi/acuity-core-pypi-prod/simple
```

---

## Best Practices

- **Never** commit sensitive credentials (passwords, API keys) to version control.
- Prefer environment variables for managing secrets.
- Use [Poetry's configuration documentation](https://python-poetry.org/docs/repositories/) for advanced setups.
- Regularly rotate credentials and audit repository access.

---

## Troubleshooting

- Ensure your credentials are correct and have access to the repository.
- If you encounter SSL or authentication errors, verify your Poetry and Artifactory versions.
- For more help, see [Poetry's troubleshooting guide](https://python-poetry.org/docs/configuration/#http-basic-authentication).

---

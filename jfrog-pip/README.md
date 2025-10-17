# JFrog Pip Integration

This guide explains how to configure `pip` to use a JFrog Artifactory repository for Python package management.

## Prerequisites

- Access to a JFrog Artifactory instance
- Valid Artifactory username and password
- The name of your PyPI repository in Artifactory

## Configuration Steps

1. **Locate or create your pip configuration file:**

    ```bash
    mkdir -p ~/.pip
    touch ~/.pip/pip.conf
    ```

2. **Edit `~/.pip/pip.conf` and add the following:**

    ```ini
    [global]
    index-url = https://<user_name>:<password>@<artifactory-host>/artifactory/api/pypi/<repo_name>/simple
    ```

    - Replace `<user_name>`, `<password>`, `<artifactory-host>`, and `<repo_name>` with your actual credentials and repository details.

## Example

```ini
[global]
index-url = https://<user_name>:<password>@gwproductengineering.jfrog.io/artifactory/api/pypi/acuity-core-pypi-prod/simple
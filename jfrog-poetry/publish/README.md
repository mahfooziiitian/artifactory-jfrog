# Publishing Python Packages with Poetry

This guide explains how to publish Python packages to JFrog Artifactory using [Poetry](https://python-poetry.org/).

---

## Prerequisites

- Ensure you have [Poetry](https://python-poetry.org/docs/#installation) installed.
- Configure your Artifactory repository in Poetry using:

    ```sh
    poetry config repositories.<REPOSITORY_NAME> https://<ARTIFACTORY_URL>/api/pypi/<REPOSITORY_NAME>
    ```

## Publishing Your Package

To publish your package, run:

```sh
poetry publish --repository <REPOSITORY_NAME> --dist-dir dist
```

**Example:**

```sh
poetry publish --repository pypi-local --dist-dir dist
```

---

## Additional Resources

- [JFrog Artifactory User Guide](https://jfrog.com/artifactory/)
- [Poetry Documentation](https://python-poetry.org/docs/)

---

> 💡 **Tip:** Make sure your credentials are set up in `~/.pypirc` or via Poetry's configuration for authentication.

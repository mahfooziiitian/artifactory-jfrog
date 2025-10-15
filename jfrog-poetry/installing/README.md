# Installing Python Packages with Poetry

Poetry makes it easy to manage dependencies for your Python projects. To add a package from a specific repository, use the following command:

```bash
poetry add --source <REPOSITORY_NAME> <PACKAGE_NAME>
```

**Example:**  
To install a package named `my_pypi_package` from the `pypi-local` repository:

```bash
poetry add --source pypi-local my_pypi_package
```

> **Tip:**  
> Replace `<REPOSITORY_NAME>` with the name of your configured repository and `<PACKAGE_NAME>` with the desired package.

For more details, refer to the [Poetry documentation](https://python-poetry.org/docs/cli/#add).

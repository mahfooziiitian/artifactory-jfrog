Integration Steps: UV with JFrog Artifactory
1. One-Time Use (Command Line)
You can directly specify the Artifactory URL with credentials in the command:
Shelluv run myscript.py --index-url https://<username>:<password>@artifactory.mycompany.com/artifactory/api/pypi/<repo>/simple``Show more lines
Replace:

<username> and <password> with your Artifactory credentials or API token.
<repo> with your Python repository name in Artifactory.


2. Persistent Setup (Project Configuration)
Use pyproject.toml to define the Artifactory index:
TOML[[tool.uv.index]]name = "artifactory"url = "https://artifactory.mycompany.com/artifactory/api/pypi/<repo>/simple"``Show more lines
Then set environment variables for authentication:
Shellexport UV_INDEX_ARTIFACTORY_USERNAME="your-username"export UV_INDEX_ARTIFACTORY_PASSWORD="your-password-or-token"Show more lines
You can add these to .bashrc or .zshrc for persistence.

🔐 Authentication Notes

UV supports Basic Auth via embedded credentials in the URL or environment variables.
For more secure setups, consider using API tokens instead of passwords.


📦 Publishing Packages
UV also supports publishing to Artifactory using:
Shelluv publishShow more lines
Ensure your credentials and repository URL are correctly configured in pyproject.toml.
# Web Sign-in to the JFrog Platform

Authenticate with the JFrog Platform easily using the `jf login` command, which launches an interactive web browser session for secure sign-in. This method is designed for manual use and does not accept command-line options. Note that it is not suitable for automation or CI/CD environments.

**Usage:**

```sh
jf login
```

After running the command, follow the prompts in your browser to complete authentication.

**Important:**  

- The `jf login` command is intended for interactive sessions only.
- For automated workflows or CI servers, use alternative authentication methods such as API keys or access tokens.

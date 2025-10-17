# File upload

## Generic Files

### Uploading Files

```bash
jf rt u [command options] <Source path> <Target path> 
jf rt u --spec=<File Spec path> [command options]
```

#### Upload a single file

Upload a file called froggy.tgz to the root of the my-local-repo repository.

```bash
jf rt u froggy.tgz my-local-repo
```

#### Upload all .zip files from a directory and its subdirectories

```bash
jf rt u "build/*.zip" my-local-repo/zipFiles/
```

#### Upload and sync a folder, deleting remote files that are not in the local source

```bash
jf rt u "build/*.zip" my-local-repo/zipFiles/ --sync-deletes="my-local-repo/zipFiles/"
```

#### upload to sepcifc repository

Collect all files located under the build directory (including subdirectories), and upload them to the my-release-local repository, under the files folder, while maintaining the original names of the artifacts. Exclude (do not upload) files, which include install as part of their path, and have the pack extension.

```bash
jf rt u "build/" my-release-local/files/ --exclusions="\*install\*pack*"
```

#### Example 5

Collect all files located under the build directory (including subdirectories), and upload them to the my-release-local repository, under the files folder, while maintaining the original names of the artifacts. Exclude (do not upload) files, which include install as part of their path, and have the pack extension.

```bash
jf rt u "build/" my-release-local/files/ --regexp --exclusions="(.*)install.*pack$"
```

#### Package all files located under the build directory (including subdirectories) into a zip archive named archive.zip , and upload the archive to the my-local-repo repository

```bash
jf rt u "build/" my-local-repo/my-archive.zip --archive zip
```

# pre-commit-trivy

Add this to your [pre-commit](https://pre-commit.com/) `.pre-commit-config.yaml` config.

You can use [trivy fs flags](https://aquasecurity.github.io/trivy/v0.34/docs/vulnerability/scanning/filesystem/) to configure Trivy.
Insert the required flags in the `args` field.

- `trivy-docker`: pre-commit will use the latest `aquasecurity/trivy` docker image and run it inside a docker container

```yaml
repos:
-   repo: https://github.com/mxab/pre-commit-trivy.git
    rev: v0.1.0
    hooks:
    -   id: trivyfs-docker
        args:
          - --skip-dirs
          - ./tests
          - . # last arg indicates the path/file to scan
```
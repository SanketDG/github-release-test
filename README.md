# GitHub release test

A small repository for experimenting with Docker publication through GitHub
Actions. The Dockerfile builds from BusyBox and runs `ls` during the build.
There is no application service or application test suite.

## Files

- `Dockerfile`: the minimal container build.
- `.github/workflows/publish-docker-on-release.yml`: Docker publication workflow.
- `.github/ISSUE_TEMPLATE/` and `.github/issue_template.md`: issue templates.

## Workflow behavior

Despite its filename, the workflow triggers on pushes to `master` and pushes
of any tag. It publishes the image `snkt/hello-world` using credentials supplied
through GitHub Actions secrets. Review the workflow before pushing changes or
tags; a push can publish an image.

## Local inspection

With Docker installed, a local build can be run without publishing:

```sh
docker build -t github-release-test:local .
```

The build downloads its base image if needed. Neither a Docker build nor the
publication workflow was run during this documentation update.

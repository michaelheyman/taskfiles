# Taskfiles

A collection of reusable Taskfiles for common development workflows.

## About Task

[Task](https://taskfile.dev/) is a task runner / build tool that aims to be simpler and easier to use than, for example,
`make`.

## Requirements

- [Task](https://taskfile.dev/#/installation) version 3.0.0 or higher installed on your system.
- [Remote Taskfiles](https://taskfile.dev/docs/experiments/remote-taskfiles) experiment enabled. You can enable it by
creating a `.taskrc.yml` file in your repository root with the following content:

    ```yaml
    # Enable experimental features
    experiments:
      # Remote Taskfiles experiment: https://taskfile.dev/docs/experiments/remote-taskfiles
      REMOTE_TASKFILES: 1
    ```

## Usage

You can include these task definitions in your projects using Task's `includes` feature. Choose either HTTPS or SSH
depending on your setup.

### Git over SSH

If you have SSH keys configured with GitHub, use:

```yaml
version: "3"

includes:
  docker:
    taskfile: git@github.com:michaelheyman/taskfiles.git//docker/Taskfile.yml?ref=main
  python:
    taskfile: git@github.com:michaelheyman/taskfiles.git//python/Taskfile.yml?ref=main
  markdown:
    taskfile: git@github.com:michaelheyman/taskfiles.git//markdown/Taskfile.yml?ref=main
  pre-commit:
    taskfile: git@github.com:michaelheyman/taskfiles.git//pre-commit/Taskfile.yml?ref=main
  terraform:
    taskfile: git@github.com:michaelheyman/taskfiles.git//terraform/Taskfile.yml?ref=main
  yaml:
    taskfile: git@github.com:michaelheyman/taskfiles.git//yaml/Taskfile.yml?ref=main
```

### Git over HTTP

If your want to leverage HTTPS, use:

```yaml
version: "3"

includes:
  docker:
    taskfile: https://github.com/michaelheyman/taskfiles.git//docker/Taskfile.yml?ref=main
  python:
    taskfile: https://github.com/michaelheyman/taskfiles.git//python/Taskfile.yml?ref=main
  markdown:
    taskfile: https://github.com/michaelheyman/taskfiles.git//markdown/Taskfile.yml?ref=main
  pre-commit:
    taskfile: https://github.com/michaelheyman/taskfiles.git//pre-commit/Taskfile.yml?ref=main
  terraform:
    taskfile: https://github.com/michaelheyman/taskfiles.git//terraform/Taskfile.yml?ref=main
  yaml:
    taskfile: https://github.com/michaelheyman/taskfiles.git//yaml/Taskfile.yml?ref=main
```

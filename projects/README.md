# projects

We define a project as a standalone analysis or application with its own set of dependencies. Unlike library packages, project packages are not intended to be used as dependencies for other packages.

## creating a project

To create a project, run the following command:

```bash
# (starting from root)
cd projects
poetry new <project-name>
```

This will create a new directory with the name `<project-name>` and a `pyproject.toml` file inside. The `pyproject.toml` file contains the project's dependencies and other metadata. You can add dependencies to the project by editing the `pyproject.toml` file or by running `poetry add <dependency>`.

When your dependencies are set, you can run `poetry install` to create a virtual environment for the project and install the dependencies.

## contents

- [`project_a`](project_a)

# Setup Python Env

> NOTICE: WORK IN PROGRESS

Setup Python Environment.

## Usage

```yaml
- uses: cdqag/setup-python-env@master
```

### Inputs

| Name                   | Description                                            | Default    |
|------------------------|--------------------------------------------------------|------------|
| `python-version`       | Version of Python to use                               | `3.10`     |
| `setup-virtualenv`     | Should setup virtualenv?                               | `false`    |
| `virtualenv-dir`       | Directory to setup virtualenv                          | `.venv`    |
| `install-poetry`       | Should install Poetry?                                 | `false`    |
| `poetry-version`       | Version of Poetry to use                               | `1.8.1`    |
| `index-url`            | Index URL to set for pip - set empty to skip           | ``         |
| `install-dependencies` | Should install dependencies?                           | `true`     |
| `install-packages`     | Install packages - set empty to skip                   | ``         |

### Example

```yaml
name: Example

on:
  workflow_dispatch:

jobs:
  example_job:
    runs-on: my-self-hosted-runner

    steps:
      - uses: cdqag/setup-python-env@master
      - run: pip --version  # This should output also location of used pip (you should see path/.venv/bin/pip)
 
```

## License

This project is licensed under the MIT License. See the LICENSE file for details.

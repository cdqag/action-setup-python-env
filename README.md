# Setup Python Env

This action:

* installs Python via [actions/setup-python@v5](https://github.com/actions/setup-python)
* (optionally) installs and activated virtualenv
* (optionally) installs [Poetry](https://python-poetry.org/)
* (optionally) sets custom [index URL](https://pip.pypa.io/en/stable/cli/pip_install/#cmdoption-i)
* (optionally) installs dependencies either via pip or Poetry
* (optionally) installs additional packages

## Usage

```yaml
- uses: cdqag/setup-python-env@v1
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
name: Setup virtualenv

on:
  workflow_dispatch:

jobs:
  example_job:
    runs-on: my-self-hosted-runner

    steps:
      - uses: cdqag/setup-python-env@v1
        with:
          setup-virtualenv: true
          install-packages: flake8 pycodestyle
      - run: pip --version  # This should output also location of used pip (you should see path/.venv/bin/pip)

```

## License

This project is licensed under the MIT License. See the LICENSE file for details.

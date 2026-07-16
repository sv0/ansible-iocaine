# Iocaine ansible role

Installs [iocaine](https://iocaine.madhouse-project.org/),
defense mechanism against LLM scrapers.

It has been tested for the following Linux distributions:

* Debian Bookworm
* Debian Trixie
* Alpine 3.24

## Requirements

* Python >=3.11 on Ansible controller host
* [ansible-core](https://pypi.org/project/ansible-core/) version >= 2.14, <2.20

As of 2026, most popular Linux distributions(Debian/Ubuntu)
have the following Python versions.

| OS | Default Python version    |
|----|---------------------------|
| Debian Bookworm | Python 3.11  |
| Debian Trixie   | Python 3.13  |
| Ubuntu 22.04    | Python 3.10  |
| Ubuntu 24.04    | Python 3.12  |
| Alpine 3.24     | Python 3.14  |

## Development

### Development requirements

* Docker
* [molecule](https://pypi.org/project/molecule/) version >=6.0, <25.0

Install development requirements

```shell
    apt-get install -y \
      direnv \
      make \
      python3 \
      python3-venv \
      docker.io \
      ruby-mdl
```

and then

```shell
    make install
```

## Testing

See [Development requirements](#development-requirements) section first.

Run the whole bunch of molecule scenario:

```shell
    make test
```

Create docker container for tests:

```shell
    make create
```

Run this role on created container:

```shell
    make converge
```

For more details, see

```shell
    make help
```

## Ansible

### Defaults

Take a look at [defaults/main.yml](defaults/main.yml) file.

### Configuration

```yaml
    iocaine_version: '3.5.0'
    iocaine_metrics_port: 42042
    iocaine_metrics_host: '127.0.0.1'
    iocaine_port: 42069
    iocaine_host: '127.0.0.1'
```

## References

* [The deadliest poison known to AI](https://iocaine.madhouse-project.org/)
* [Getting started with iocaine](https://iocaine.madhouse-project.org/documentation/3/getting-started/)

### Other usefull tools

* [ruby-mdl](https://github.com/markdownlint/markdownlint) markdown lint tool
* [direnv](https://github.com/direnv/direnv) loads and unloads environment variables
    depending on the current directory.

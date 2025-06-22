# Ansible Role: Perl

[![CI](https://github.com/blackstar257/ansible-perl/workflows/CI/badge.svg)](https://github.com/blackstar257/ansible-perl/actions?query=workflow%3ACI)
[![Ansible Role](https://img.shields.io/ansible/role/d/blackstar257/perl)](https://galaxy.ansible.com/blackstar257/perl/)
[![Downloads](https://img.shields.io/ansible/role/dt/blackstar257/perl)](https://galaxy.ansible.com/blackstar257/perl/)

An Ansible role that installs and manages Perl on various Linux distributions, including CPAN module management via cpanm.

## Requirements

* Ansible 2.10 or higher
* Target systems must be supported Linux distributions (Ubuntu, Debian, RHEL/CentOS/Rocky/Alma Linux)
* `community.general` collection (for the `cpanm` module)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Variable                 | Default                                            | Description                                               |
| ------------------------ | -------------------------------------------------- | --------------------------------------------------------- |
| perl_cpanm_version       | "1.7907"                                           | CPAN Minus version to install                             |
| perl_cpanm_path          | "/usr/local/bin/cpanm"                             | Path where cpanm will be installed                       |
| perl_cpanm_url           | "https://raw.githubusercontent.com/..."           | URL to download cpanm script                              |
| perl_cpanm_modules       | []                                                 | List of Perl modules to install via cpanm                |
| perl_cpanm_installdeps   | false                                              | Install dependencies for modules                          |
| perl_cpanm_notests       | false                                              | Skip tests during module installation                     |
| perl_cpanm_force         | false                                              | Force installation even if tests fail                     |
| perl_cpanm_verbose       | false                                              | Enable verbose output during installation                 |

### CPAN Module Installation

The `perl_cpanm_modules` variable accepts a list of module names to install:

```yaml
perl_cpanm_modules:
  - JSON
  - DBI
  - Mojolicious
  - DateTime
```

## Dependencies

* `community.general` collection

Install with:

```bash
ansible-galaxy collection install community.general
```

## Example Playbook

### Basic usage

```yaml
- hosts: all
  become: true
  roles:
    - blackstar257.perl
```

### Install Perl with specific modules

```yaml
- hosts: all
  become: true
  vars:
    perl_cpanm_modules:
      - JSON
      - LWP::UserAgent
      - DateTime
      - Mojolicious
  roles:
    - blackstar257.perl
```

### Advanced configuration

```yaml
- hosts: all
  become: true
  vars:
    perl_cpanm_modules:
      - JSON::XS
      - DBI
      - DBD::mysql
    perl_cpanm_installdeps: true    # Install dependencies
    perl_cpanm_notests: true        # Skip tests for faster installation
    perl_cpanm_verbose: true        # Verbose output
  roles:
    - blackstar257.perl
```

### Use specific cpanm version

```yaml
- hosts: all
  become: true
  vars:
    perl_cpanm_version: "1.7907"
    perl_cpanm_modules:
      - Carton
      - Plack
  roles:
    - blackstar257.perl
```

## Supported Platforms

* Ubuntu 20.04 (Focal), 22.04 (Jammy), 22.10 (Kinetic)
* Debian 10 (Buster), 11 (Bullseye), 12 (Bookworm)
* RHEL/CentOS 7, 8, 9
* Rocky Linux 8, 9
* AlmaLinux 8, 9
* Fedora 37, 38, 39

## Testing

This role is tested using Molecule with Docker.

```bash
# Install dependencies
pip install molecule molecule-plugins[docker] docker

# Run tests
molecule test

# Test with specific distro
MOLECULE_DISTRO=ubuntu2204 molecule test
```

## Available Test Distributions

* ubuntu1804
* ubuntu2004
* ubuntu2204
* debian10
* debian11
* centos7
* centos8
* rockylinux8
* rockylinux9

## Important Notes

* **Privileges Required**: This role requires `become: true` for package installation and cpanm setup
* **Internet Access**: The role downloads cpanm from GitHub and CPAN modules from the internet
* **Performance**: Installing many modules or modules with complex dependencies may take time
* **Testing**: Use `perl_cpanm_notests: true` to skip module tests for faster installation

## License

MIT

## Author Information

This role was originally created by Pieterjan Vandaele and is now maintained by blackstar257.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests: `molecule test`
5. Submit a pull request

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for detailed release notes and version history.

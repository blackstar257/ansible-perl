# Ansible Role: Perl

[![Ansible Role](https://img.shields.io/badge/role-blackstar257.perl-blue.svg)](https://galaxy.ansible.com/blackstar257/perl/)
[![Build Status](https://travis-ci.com/blackstar257/ansible-perl.svg?branch=master)](https://travis-ci.com/blackstar257/ansible-perl)

Ansible role which manages Perl installation and provides cpan_module, to install modules from CPAN.

## Requirements

This role requires Ansible 2.8 or higher.

## Role Variables

| Name                   | Default              | Description                                 |
| ---------------------- | -------------------- | ------------------------------------------- |
| perl_cpanm_version     | 1.7907               | The CPAN release version                    |
| perl_cpanm_path        | /usr/local/bin/cpanm | The CPAN script location                    |
| perl_cpanm_modules     | []                   | List of modules to install with cpanm       |
| perl_cpanm_installdeps | false                | Toggle to install dependencies for packages |
| perl_cpanm_notests     | false                | Toggle to run tests packages                |

## Dependencies

None

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: blackstar257.perl
      perl_cpanm_modules:
        - JSON
```

## License

Licensed under the MIT License. See the LICENSE file for details.

## Author Information

Original Pieterjan Vandaele
Forked by blackstar257

# Ansible Role: Perl

[![Ansible Role](https://img.shields.io/badge/role-blackstar257.perl-blue.svg)](https://galaxy.ansible.com/blackstar257/perl/)
[![Build Status](https://travis-ci.org/blackstar257/ansible-perl.svg?branch=master)](https://travis-ci.org/blackstar257/ansible-perl)

Ansible role which manages Perl installation and provides cpan_module, to install modules from CPAN.

## Requirements

This role requires Ansible 2.0 or higher.

## Role Variables

| Name               | Default              | Description               |
| ------------------ | -------------------- | ------------------------- |
| perl_cpanm_version | 1.7907               | The CPAN release version  |
| perl_cpanm_path    | /usr/local/bin/cpanm | SThe CPAN script location |

## Dependencies

None

## Example Playbook

```yaml
- hosts: all
  roles:
    - blackstar257.perl
```

## License

Licensed under the MIT License. See the LICENSE file for details.

## Author Information

Original Pieterjan Vandaele
Forked by blackstar257

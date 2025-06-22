# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0] - 2025-01-27

### Added
- Support for Ansible 2.10+
- Support for Rocky Linux and AlmaLinux
- GitHub Actions CI/CD pipeline
- Modern molecule testing configuration
- Comprehensive verification tests
- New configuration options: `perl_cpanm_force` and `perl_cpanm_verbose`
- Ansible-lint and yamllint configuration files
- Requirements.yml for collection dependencies
- Handlers directory for future extensibility
- Comprehensive documentation in README

### Changed
- Migrated from Travis CI to GitHub Actions
- Updated to latest cpanm version (1.7907)
- Modernized task syntax with FQCN (Fully Qualified Collection Names)
- Enhanced platform-specific variable files
- Improved error handling and idempotency
- Updated platform support matrix
- Enhanced README with modern badges and examples

### Improved
- Code quality with linting integration
- Testing coverage across multiple distributions
- Documentation with detailed usage examples
- Variable organization and descriptions

## [1.x.x] - Previous Versions

Previous versions were maintained by the original author Pieterjan Vandaele.
For historical changes, please refer to the git commit history. 
![Logo](https://raw.githubusercontent.com/idealista/jira-role/master/logo.gif)

[![Build Status](https://travis-ci.org/idealista/jira-role.png)](https://travis-ci.org/idealista/jira-role)

# Jira Ansible role

This Ansible role installs Atlassian Jira in a Debian environment. The app is deployed to a Tomcat server and will expose the endpoint `yourip:8080`.

- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Getting Started

These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will deploy [Atlassian Jira](https://www.atlassian.com/software/jira/) to a Tomcat server in a Debian system.

### Prerequisities

Ansible 2.3.1.0 version installed.
Inventory destination should be a Debian environment.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) (version 1.25) with [Vagrant](https://www.vagrantup.com/) as driver (with [landrush](https://github.com/vagrant-landrush/landrush) plugin) and [VirtualBox](https://www.virtualbox.org/) or [Docker](https://www.docker.com/) as provider.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

``` yml
- src: idealista.jira-role
  version: 1.0.0
  name: jira
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

``` yml
---
- hosts: someserver
  roles:
    - role: jira
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties.

## Testing

### Using Vagrant as provider
```
molecule test
```

### Using Docker as provider
```
molecule test --driver docker
```

See molecule.yml to check possible testing platforms. As a reminder, our tests are just compatible with Molecule 1.x

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.3.1.0-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/jira-role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

* **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/jira-role/contributors) who participated in this project.

## License

![Apache 2.0 Licence](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

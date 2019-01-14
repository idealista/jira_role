![Logo](https://raw.githubusercontent.com/idealista/jira_role/master/logo.gif)

[![CircleCI](https://circleci.com/gh/idealista/jira_role.svg?style=svg)](https://circleci.com/gh/idealista/jira_role)

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

Ansible 2.4.5.0 version installed.
Inventory destination should be a Debian environment.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

``` yml
- src: idealista.jira_role
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

There are some variables in [vars](vars) folder that help with the database configuration. Overriding them could be a bit difficult due to [Ansible variable precedence](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#variable-precedence-where-should-i-put-a-variable) so, in case you need to set new values, our recommendation is to have a `vars` folder in your playbook folder, put there a vars file with your preferred values and include them in your main playbook with [include_vars](https://docs.ansible.com/ansible/latest/modules/include_vars_module.html).

## Testing

```sh
$ pipenv install -r test-requirements.txt --python 2.7
$ pipenv run molecule test
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.3.1.0-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/jira_role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

* **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/jira_role/contributors) who participated in this project.

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

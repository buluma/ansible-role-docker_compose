# [Ansible role docker_compose](#ansible-role-docker_compose)

Install docker_compose.

|GitHub|Issues|Pull Requests|Version|Downloads|
|------|------|-------------|-------|---------|
|[![github](https://github.com/buluma/ansible-role-docker_compose/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-docker_compose/actions/workflows/molecule.yml)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-docker_compose.svg)](https://github.com/buluma/ansible-role-docker_compose/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-docker_compose.svg)](https://github.com/buluma/ansible-role-docker_compose/pulls/)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-docker_compose.svg)](https://github.com/buluma/ansible-role-docker_compose/releases/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/docker_compose)](https://galaxy.ansible.com/ui/standalone/roles/buluma/docker_compose/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-docker_compose/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  vars:
    docker_compose_url:
      "https://github.com/docker/compose/releases/download/{{ docker_compose_version
      }}/docker-compose-{{ ansible_system | lower }}-{{ docker_compose_architecture
      }}"

  roles:
    - role: buluma.docker_compose
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-docker_compose/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-docker_compose/blob/master/defaults/main.yml):

```yaml
---
# defaults file for docker_compose

# The version of Docker compose to install.
# The versions `1.*` do not start with a `v`.
# The versions `2.*` do start with a `v`.
# You can check available versions here:
# https://github.com/docker/compose/releases
docker_compose_version: "v2.24.1"

# Where to download the docker binary from.
docker_compose_url:
  "https://github.com/docker/compose/releases/download/{{ docker_compose_version }}/docker-compose-{{ ansible_system | lower }}-{{ docker_compose_architecture
  }}"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-docker_compose/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub |
|-------------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-docker_compose/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/r/robertdebock/alpine)|all|
|[EL](https://hub.docker.com/r/robertdebock/enterpriselinux)|all|
|[Debian](https://hub.docker.com/r/robertdebock/debian)|all|
|[Fedora](https://hub.docker.com/r/robertdebock/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/robertdebock/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-docker_compose/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-docker_compose/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

# VoltPop Ansible Implementation

Git hosted Ansible automation, but fancy.

## What even is this and how does it work?

TL;DR: This is ansible in a pipenv

* On commit, the github repo fires webhooks to VoltPop's Pub/Sub server
* The Listener agent (on VoltPop's Docker servers) receives the Pub/Sub message
* VoltPop's Docker Servers pull in and apply the changes specified in the message.

## Ansible + Pipenv

[Ansible](https://docs.ansible.com/ansible/latest/user_guide/index.html#getting-started) is a pfawesome automation and configuration management solution. A [Pipenv](https://pipenv.pypa.io/en/latest/) is a python3 environment which encapsulates all of the necessary packages and bits and keeps them in sync.

### Submodules

The ansible environment uses three submodules for security purposes:
* roles
* playbooks
* vars

are each independent repositories. in order to initialize these modules, run:

`git submodule update --init`

### Pipenv usage

To configure the environment (typically on download), run:

`pipenv install`

To start a shell in the pyton environment, run:

`pipenv shell`

To run a single one off in the python3 environment, run:

`pipenv run <COMMAND>`

If, in the course of development you find that you need to extend Ansible with a Python module, add it to the `Pipfile` and re-run:

`pipenv install`

## Pub/Sub 

This Ansible instance is meant to be used in conjunction with the VoltPop vp-listener and vp-announce services.

* [vp-listener](https://github.com/voltpop/vp-listener)
* [vp-announce](https://github.com/voltpop/vp-announce)

## Configuration

an .env file holds the path to the ansible config.
* set ENVVAR `ANSIBLE_DIR` to the location of the checkout. pipenv's .env file will use that value.

## Development

This service is wrapped in pipenv, requiring only git and python3 to be present to configure a machine
(i.e. no SSH needed).

To run an interactive development shell, use `pipenv shell`

This will create a local development / running environment with all of the software pre-configured.

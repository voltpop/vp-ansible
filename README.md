# Ansible Pipenv
TESTING
Git hosted Ansible automation

## Usage

This is intended to be used in conjunction with the voltpop-announce / voltpop-listener services.

With this repository configured to send a webhook to a voltpop-announce service instance with each commit, 
Listener services running on remote machines will know that it's time to git pull their own repositories 
and refresh their configurations.

* [vp-listener](https://github.com/voltpop/vp-listener)
* [vp-announce](https://github.com/voltpop/vp-announce)

## Configuration

an .env file holds the path to the ansible config. This is going to be configured to use the root path of the current git checkout.

## Development

This service is wrapped in pipenv, requiring only git and python3 to be present to configure a machine
(i.e. no SSH needed).

To run an interactive development shell, use `pipenv shell`

This will create a local development / running environment with all of the software pre-configured.

For more information about pipenv, see: https://pipenv.pypa.io/en/latest/

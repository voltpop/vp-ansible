# VoltPop Ansible Playbooks

## Usage

VoltPop's Ansible Playbooks all use the same invocation scheme:

```
ansible-playbook playbooks/<consumer>/service/<service>/<operation>_<service>.yml --extra-vars varsfile=vars/<clientname>.yml --ask-become-password --ask-vault-password
```

These playbooks are to be used to manage the client services.

## Organization

Each service role should have a corresponding playbooks directory that contains playbooks for the following:

* Install the service (read the vars file and invoke the role)
* Bounce / restart the service (whether via restart or stop / start chain)
  * These playbooks support the `stop` and `start` tags passed with `-t|--tags`
* Uninstall the service
  * These playbooks require that _all_ client data be saved and retrieved such that we can hand it over.

These playbooks, due to their invocation, do not allow for actions across client spaces, only one client may be provided per invocation.
Playbooks in the `playbooks` directory (i.e. not in a service role directory) allow for actions at the server level, meaning:

The playbooks in the top level should be looper playbooks for the nested service specific playbooks.

## Development

All of these services are designed to be applied to the localhost only, hence it's in development mode already! when you're ready to
push these changes to a host, simply open a PR. when it's merged the changes will be pulled in and applied automagically.

This is the way.

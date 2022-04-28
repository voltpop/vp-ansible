VoltPop Mail Server
=========

Deploy a Postfix Docker instance configured to forward mail.

Requirements
------------

* docker-compose

Role Variables
--------------

| *Name* | *Description* |
| `postfix_db | Postfix Database |
| `postfix_db_user | Postfix Database User | 
| `postfix_db_pass | Postfix Database Password |


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars_files:
        - "{{ varfile }}"
      roles:
         - { role: username.rolename }
    
    invocation:
        ansible-playbook playbooks/test_mail.yml -Ke "varsfile='/path/to/vars/file.yml'" --ask-vault-pass

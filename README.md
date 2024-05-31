template
=========

Template for Ansible role monorepos

Requirements
------------

None

Role Variables
--------------

`config`: path to a (vault-encrypted) configuration file (see the molecule folder for an unencrypted example)
`repo`: borgbecue repository URL
`timer_oncalendar`: timer configuration string (systemd style)
`repo_keyscan_val`: a `known_hosts` entry for a Borg server hosting the repo we want to send backups to. To obtain, run *on the Borg server* `ssh-keyscan -H <address>`, where `<address>` is whatever `config.server.ip` is set to. This is to work around SSH host key checking without resorting to `StrictHostKeyChecking=no` which leaves us vulnerable to a MITM attack.


Dependencies
------------

None

Example Playbook
----------------

```yaml
roles:
    - role: genlab.ansible_borgbecue
```

License
-------

BSD

Author Information
------------------

corvus-migratorius@proton.me

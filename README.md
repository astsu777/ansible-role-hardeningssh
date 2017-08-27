Ansible Role: SSH Hardening
=========

The purpose of this role is to harden the configuration of the SSHD service on a Linux server.
Note that this role disables the SSH root login and enforces SSH key-pair authentication: **make sure you have a key pair already defined!**

Requirements
------------

It is required to have a user able to login via SSH with a public/private key pair. Otherwise, you will lose remote SSH connection to your server.

Role Variables
--------------

No variables for this role.

Dependencies
------------

No dependencies from other roles required.

Example Playbook
----------------

Here is a simple example playbook to use this role:

```
hosts: all
user: myuser
become: true
roles:
  - { role: hardeningssh, tags: [ 'hardeningssh' ] }
```

License
-------

MIT / BSD

Author Information
------------------

My name is Gaétan. You can follow me on [Twitter](https://twitter.com/gaetanict)

Website: [ICT Pour Tous](https://www.ictpourtous.com)

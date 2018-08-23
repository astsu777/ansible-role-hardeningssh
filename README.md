Ansible Role: SSH Hardening
=========

The purpose of this role is to harden the configuration of the SSHD service on a Linux server.
Note that this role disables the SSH root login and enforces SSH key-pair authentication: **make sure you have a key pair already defined!**

(Optional) It is also possible to add two-factor authentication (2FA) using Google Authenticator using a variable.


Two-Factor Authentication
-------------------------

By default, 2FA will be disabled for users who have not configured it yet. The only supported method for this role is, for the moment, Google Authenticator. In order to configure it for a user, you have to use the command **google-authenticator** and follow the wizard (it is very simple).

**Once 2FA has been configured, it will be enforced for that user!**


Requirements
------------

It is required to have a user able to login via SSH with a public/private key pair. Otherwise, you will lose remote SSH connection to your server.


Role Variables
--------------

Two variables for this role: one is to determine which multi-factor authentication method (called **mfa**) and the other one limits the SSH connection to certain users (called **alloed_ssh_users**). By default, 2FA is disabled.

Here is the default configuration of the variable:

```
mfa: none
allowed_ssh_users: johndoe
```

If you want to enable 2FA, you can use the value **google-authenticator** and it will be enabled (although, not enforced).


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

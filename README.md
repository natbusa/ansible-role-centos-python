Python
===============

Adapted from [python-from-source](https://github.com/naiquevin/python-from-src) by Vineet Naik <naikvin@gmail.com>. Ansible role for installing a particular version of Python from
source.

Requirements
------------

None

Role Variables
--------------

The only role vars that the user needs to worry about are:

- `pyfsrc_version`: The version of python to install
- `pyfsrc_make_default`: Whether to make this version of python the
  default version on the system.
- `pyfsrc_force_install`: Install again even if the specified version
  is already found.
- `pyfsrc_ssl_support`: add python support for ssl
- `pyfsrc_install_pip`: install pip and setuptools

Dependencies
------------

None

Example Playbook
----------------

eg:

```
    - name: Install python
      hosts: localhost
      sudo: yes
      - role: natbusa.centos-python
        pyfsrc_version: 3.5.2
        pyfsrc_make_default: yes
        pyfsrc_ssl_support: yes
        pyfsrc_install_pip: yes
```

The above playbook will install python version 3.4.3.

The role can be used multiple times with different value of
`pyfsrc_version` to install different versions. This can be useful for
setting up an environment for testing a python lib against multiple
versions by using tox for eg.

License
-------

MIT

Author Information
------------------

Vineet Naik <naikvin@gmail.com>
Natalino Busa <natalino.busa@gmail.com>

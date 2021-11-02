fapolicyd_role
=========
Installs and configures the File Access Policy daemon on Red Hat systems.

This role also updates the `/etc/fapolicyd/fapolicyd.trust` file, and allows this state to be maintained in a git repository.

Requirements
------------

None.

Role Variables
--------------

This role takes an array `trusted_apps` and updates the `/etc/fapolicyd/fapolicyd.trust` configuration on the host. eg;
```
trusted_apps:
 - path: /usr/local/bin/cowsay
   size: 2195456
   checksum: 8adee1c9ecc498d2e136c51fc553b9ecabf0bfff46335f0b9010c821580c022f
```

Dependencies
------------

None.

Example Playbook
----------------

    - name: Update fapolicyd
      hosts: all
      become: true
      roles:
        - { role: shaneboulden.fapolicyd_role }

License
-------

BSD

Author Information
------------------

dev@stb.id.au


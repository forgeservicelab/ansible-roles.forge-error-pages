FORGE Error Pages
=================

Installs FORGE specific custom error pages and leaves configuration stubs for the webserver to use them.
Custom error pages are usually handler at the virtual host level. To pick up the configuration add the following line to your virtual host configuration where it may be relevant:

### Nginx
```
include /etc/nginx/conf.d/*.extra;
```

### Apache
```
IncludeOptional conf.d/*.extra
```

Requirements
------------

This role does **NOT** install a webserver. It expects either apache or nginx to be installed on the target system.

Role Variables
--------------

- `target_webserver` - The webserver installed on the target system. One of `apache` or `nginx`

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: forge_error_pages, target_webserver: nginx }
```

License
-------

GPLv3

Author Information
------------------

FORGE Service Lab

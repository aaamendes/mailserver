mailserver
=========

Configures mailserver using postfix, dovecot and opendkim.
A letsencrypt certificate will be requested using **standalone** method.
Make sure port 80 isn't used on your new mailserver
while running the playbook.

<img src="https://img.shields.io/badge/License-MIT-blue.svg">

### Tested on
[![Rocky Linux](https://img.shields.io/badge/Rocky%20Linux-10B981?logo=rockylinux&logoColor=fff)](#)

Requirements
------------

Role Variables
--------------

| variable | type | comment |
| --- | --- | --- |
| debug | bool | Set to `true` for some extra info. |
| mxdomain | string | Your mx record domain. |
| domain | string | Your mailfrom domain. By default the subdomain is cut. |
| certbot_email | string | Your email for registration with letsencrypt. |
| certbot_flags | string | Should be fine as it is. |
| dkim_selector | string | Set it to what you like. It's the selector for dkim, could also be something like YYYYMMDD, e.g. 20240818. The path to your public key will be `/etc/opendkim/keys/mailfromdomain/20240818.txt` |
|fullchain_path | string | Should be fine as it is. It's where letsencrypt saves your certificate |
| privkey_path | string | Same as above. |

Dependencies
------------

Example Playbook
----------------

See `tests/test.yml`.

Author Information
------------------

Check out https://amendes.me

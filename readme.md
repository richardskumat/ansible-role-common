ansible-role-common
=========

This role shares common tasks that I run across all my devices/vms/cts.

It has tasks for debian 7-9, raspbian and centos 7.

Links
------------

Gitlab:

https://gitlab.com/richardskumat/ansible-role-common

Gitlab-ci:

https://gitlab.com/richardskumat/ansible-role-common/pipelines

Github:

https://github.com/richardskumat/ansible-role-common

Travis:

https://travis-ci.org/richardskumat/ansible-role-common

Requirements
------------

I mostly use latest ansible version from a python2 virtualenv.

On 20190717, this is ansible 2.8.x.

Role Variables
--------------

These are unused vars from a time I used squid3 to cache local yum and
apt-get runs.

```
# apt.conf
apt_proxy_user: proxy_user
apt_proxy_password: proxy_pass
apt_proxy_url: 127.0.0.1
apt_proxy_port: 3128
apt_proxy_http: http
```

Debian and Raspbian mirrors, used in a templating task.

```
apt_src_main_url: 'http://cdn-fastly.deb.debian.org/debian'
apt_src_security_url: 'http://security.debian.org/'
raspbian_debian_mirrors: 'http://raspbian.raspberrypi.org/raspbian/'
raspbian_specific_mirrors: 'http://archive.raspberrypi.org/debian/'
```

I prefer to use yum-cron so here are some vars for a templating task.

```
# yum-cron template
update_cmd: 'default'
update_messages: 'yes'
download_updates: 'yes'
apply_updates: 'yes'
random_sleep: '360'
system_name: 'None'
emit_via: 'stdio'
output_width: '80'
email_from: 'root@localhost'
email_to: 'root'
email_host: 'localhost'
group_list: 'none'
group_package_types: 'mandatory, default'
debuglevel: '-2'
mdpolicy: 'group:main'
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

```
- hosts: servers
  roles:
    - { role: ansible-role-common }
```

License
-------

gplv3

Author Information
------------------

None at this time.

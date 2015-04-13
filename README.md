php-fpm-role
============


Requirements
------------

- Ubuntu Server 14.04 LTS
- Ansible 1.5+


Role Variables
--------------

```yml
fpm_user: nobody
fpm_group: nobody

fpm_listen: '/var/run/php5-fpm.sock'
fpm_listen_user: nobody
fpm_listen_group: nobody
fpm_listen_mode: 0666

fpm_pm: dynamic
fpm_max_requests: 999
fpm_max_children: 64
fpm_start_servers: 8
fpm_min_spare_server: 8
fpm_max_spare_server: 32
```


Dependencies
------------

- qianka.ubuntu-common


Example Playbook
----------------

```yml
- hosts: all
  user: root
  vars:
    ubuntu_apt_mirror: http://mirrors.aliyun.com/ubuntu

  roles:
    - { role: qianka.php-fpm,
        listen: 127.0.0.1:9000
        fpm_user: gsbot,
        fpm_group: gsbot
      }

```


License
-------


Author Information
------------------

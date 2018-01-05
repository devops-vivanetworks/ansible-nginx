# shared/nginx #

Role for install and configure default nginx setting

## Requirements ##

Ansible 2.0

## Role Variables ##

### Defaults ###

    - name: nginx_ssl_dir
      desc: Directory for SSL certificats
      value: "{{ nginx_etc_dir }}/ssl"

    - name: nginx_sites_available_dir
      desc: Directory for sites-available
      value: "{{ nginx_etc_dir }}/sites-available"

    - name: nginx_sites_enabled_dir
      desc: Directory for sites-enabled
      value: "{{ nginx_etc_dir }}/sites-enabled"

    - name: nginx_upstream_dir
      desc: Directory for upstream server declarations
      value: "{{ nginx_etc_dir }}/upstream"

    - name: nginx_worker_connection
      desc: Number of worker connections
      value: 1024

    - name: nginx_worker_process
      desc: Number of worker processes
      value: auto

    - name: nginx_keepalive_timeout
      desc: Keepalive Timeout
      value: 75

### Vars ###

    - name: nginx_service_name
      value: nginx
      desc: Name for nginx service

    - name: nginx_packages
      value: nginx
      desc: Name for nginx packages

    - name: nginx_user
      value: nginx
      desc: User to run nginx as

    - name: nginx_etc_dir
      value: /etc/nginx
      desc: Nginx etc directory

    - name: nginx_conf_dir
      value: "{{ nginx_etc_dir}}/conf.d"
      desc: Directory for additional configurations

## Dependencies ##

None.

## Example Playbook ##

    - hosts: servers
      roles:
        - role: shared/ansible-nginx

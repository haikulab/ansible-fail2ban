ansible-debian-fail2ban for Debian 8 Jessie
================

Ansible role to install fail2ban with basic configuration to get up and running.

## Overwriting Variables

The `vars/main.yml` file should contain your list of packages you want to install in order to override defaults found in `defaults/main.yml`. Additionally, you can overwrite the variables as part of your playbook.

```yml
ips_to_whitelist:
  - 1.2.3.4/32
  - 4.5.6.0/24
```

## Notification sending using mail

By default from version 0.8.1 fail2ban started using sendmail as the notification sending. If you want to use `mail` from `mailutils`, set `notification_sending: mail` in your `playbook.yml` file.

## Enable SSH DDOS settings

Set `ssh_ddos: true`  in your `playbook.yml` file.

## Enable Nginx HTTP Auth settings

__Ansible checks for existance of `/var/log/nginx/error.log` to determine if this rule can be enabled.__

Set `nginx_http_auth: true`  in your `playbook.yml` file.

__Note: Some packages will already be in place with default Ubuntu install but there is no harm in making sure.__

## Debugging

If you run into errors, uncomment the `- debug: msg="{{ ... }}"` statements.

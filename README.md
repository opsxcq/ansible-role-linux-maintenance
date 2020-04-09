# Debian maintenance tasks

This task is meant to clean up your Debian 10 (butster) from time to time.

This task executes:

 - Clean up stopped docker containers.
 - Clean up unused docker networks.
 - Clean up unused docker images.
 - Clear apt cache.
 - Refresh gpg keys.
 - Delete all compressed logs on `/var/log` and subdirectories.

> This image DON'T purge docker volumes for the sake of safety

# Example playbook

```yml
- hosts: all
  vars:
    maintenance_script:
      apt update
      apt upgrade
  tasks:
  - name: My things
    debug: msg="Some additional task here"
  roles:
    - opsxcq.linux_maintenance
```

# Example requirements.yml

```yml
- src: git+https://github.com/opsxcq/ansible-role-host-backup.git
  name: "opsxcq.host_backup"
```


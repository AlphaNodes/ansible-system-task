# Ansible Role: system-task

Run system tasks

- service_restart: restart system service
- supervisor_restart: restart supervisor job

## Example Playbook

    - hosts: server-name
      vars:
        system_task_name: service_restart
        system_task_service_name: php7.0-fpm
      roles:
        - AlphaNodes.system-task

## License

GPL Version 3

## Author Information

This role was created in 2018 by [AlphaNodes](https://alphanodes.com/).

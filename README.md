# Ansible Role: system-task

Run system tasks

- service_restart: restart system service
- supervisor_restart: restart supervisor job

## Dependencies

  none

## Installation

### Ansible 2+

Using ansible galaxy cli:

```bash
ansible-galaxy install alphanodes.system-task
```

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
system_task_name: ''
```

`system_task_name` can be set to 'service_restart', 'supervisor_restart' or 'reboot'.


```
system_task_reboot_delay: 10
```

Seconds of deploy for reboot.


```
system_task_reboot_timeout: 180
```

Maximum seconds to wait for machine to reboot and respond to a test command.
This timeout is evaluated separately for both network connection and test command success so the maximum execution time for the module is twice this amount.


```
system_task_reboot_msg:
```

Message for reboot.


```
system_task_service_name: ''
```

Name of service, which should be restarted.


```
system_task_service_reload: no
```

Use reload instead of restart for service restart for `system_task_service_name`.


```
system_task_supervisor_job: ''
```

Name of supervisor job, which should be restarted.


## Example Playbook

```yaml
- hosts: server-name
  vars:
    system_task_name: service_restart
    system_task_service_name: php7.0-fpm
  roles:
    - AlphaNodes.system-task
```

## License

GPL Version 3

## Author Information

This role was created in 2018 by [AlphaNodes](https://alphanodes.com/).

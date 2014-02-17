# Common Role for Ansible

This role configures common server settings that are generally used across all server instances. The following items are addressed:

* Setting the `hostname`
* Configure defaults like:
  - Locale
  - Timezone
  - Editor
  - Unattended upgrades (security)
* Adding an Ansible message to MOTD
* Root email forwarding to a specified admin
* Installing common packages

__Note:__ This role applies a fairly opinionated set of "common" tasks. Feel free to add/remove based on your own preferences.

## Requirements

This role requires [Ansible](http://www.ansibleworks.com/) version 1.4 or higher and the Debian/Ubuntu platform.

## Role Variables

The variables that can be passed to this role and a brief description about
them are as follows:

```yaml
# The default server-wide locale
locale: 'en_US.UTF-8'

# The default server-wide timezone
timezone: 'Etc/UTC'

# The default system editor
default_editor: '/usr/bin/vim.basic'

# The default recipient of various reports and notifications
sysadmin_email: 'root@localhost'

# The default user group used for "sudo" access
sysadmin_group: 'admin'
```

## Examples

1. Configure server common settings using the defaults

    ```yaml
    ---
    - name: Apply common settings to all nodes
      hosts: all
      roles:
        - common
    ```

2. Configure server common settings with Emacs as the default editor

    ```yaml
    ---
    - name: Apply common settings to all nodes
      hosts: all
      roles:
        - { role: common,
            default_editor: '/usr/bin/emacs23-x'
          }
    ```

## Dependencies

None.

## License

MIT.

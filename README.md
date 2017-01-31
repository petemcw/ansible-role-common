# Common Role for August Ash Ansible Runs

[![Build Status](https://travis-ci.org/petemcw/ansible-role-common.svg?branch=master)](https://travis-ci.org/petemcw/ansible-role-common)

This role configures common settings that are generally used across all
server instances. The following items are addressed:

* Installing common packages
* Configure miscellaneous defaults like:
  - Locale
  - Text editor

## Role Variables

The variables that can be passed to this role and a brief description about
them are as follows:

```yaml
# Locales to generate (The first one will be the default)
common_locales:
  - en_US.UTF-8
```

## Examples

1. Configure common role without the defaults:

    ```yaml
    ---
    - name: Apply common settings to all nodes
      hosts: all
      roles:
        - role: common
          common_locales: [en_US.UTF-8, en_GB.UTF-8]
    ```

## Dependencies

None.

## License

MIT

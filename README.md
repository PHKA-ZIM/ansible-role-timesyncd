# Timesyncd automation with ansible

## Installation steps

- Go to you ansible project folder
- Add following to your requirements file

```
- src: https://github.com/PHKA-ZIM/ansible-role-timesyncd
  name: ansible-role-timesyncd
```

- Install to project roles path
```
ansible-galaxy install -r requirements.yml --roles-path ./roles
```

## Use ansible-role-timesyncd

- Import role and override role variables, e.g.
```
- name: Setup timesyncd
  hosts: localhost
  connection: local
  roles:
    - role: ansible-role-timesyncd
      ntp: 'ntp.ubuntu.com'
      timezone: 'Etc/UTC'
```

- All available role vars can be found in `defaults`

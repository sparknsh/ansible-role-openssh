# Ansible Role: openssh

#### Version: 1.0.0

[![](https://img.shields.io/badge/role-sparknsh.openssh-blue.svg)](https://galaxy.ansible.com/sparknsh/openssh)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-openssh) and [GitHub](https://github.com/sparknsh/ansible-role-openssh) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-openssh)

## Role Variables

```yaml
openssh__port: '22'
openssh__address_family: 'any'

openssh__listen_address:
  - '0.0.0.0'
  - '::'

openssh__host_key:
  - /etc/ssh/ssh_host_rsa_key
  - /etc/ssh/ssh_host_ecdsa_key
  - /etc/ssh/ssh_host_ed25519_key

openssh__rekey_limit: 'default none'

openssh__syslog_facility: 'AUTH'
openssh__loglevel: 'INFO'

openssh__login_grace_time: '2m'
openssh__permit_root_login: 'prohibit-password'
openssh__scrict_modes: 'yes'
openssh__max_auth_tries: '6'
openssh__max_sessions: '10'

openssh__pub_key_authentication: 'yes'

openssh__authorized_key_file: '.ssh/authorized_keys .ssh/authorized_keys2'

openssh__authorized_prinicpals_file: 'none'

openssh__authorized_keys_comman: 'none'
openssh__authorized_keys_command_user: 'nobody'

openssh__host_based_authentication: 'no'
openssh__ignore_user_known_hosts: 'no'
openssh__ignore_rhosts: 'yes'

openssh__password_authentication: 'yes'
openssh__permit_empty_passwords: 'no'

openssh__challenge_response_authentication: 'no'

openssh__kerberos_authentication: 'no'
openssh__kerberos_or_local_passwd: 'yes'
openssh__kerberos_ticket_cleanup: 'yes'
openssh__kerberos_get_afs_token: 'no'

openssh__gssapi_authentication: 'no'
openssh__gssapi_cleanup_credentials: 'yes'
openssh__gssapi_strict_acceptor_check: 'yes'
openssh__gssapi_key_exchange: 'no'

openssh__use_pam: 'yes'

openssh__allow_agent_forwarding: 'yes'
openssh__allow_tcp_forwarding: 'yes'
openssh__gateway_ports: 'no'
openssh__x11_forwarding: 'yes'
openssh__x11_display_offset: '10'
openssh__x11_use_localhost: 'yes'
openssh__permit_tty: 'yes'
openssh__print_motd: 'no'
openssh__print_last_log: 'yes'
openssh__tcp_keep_alive: 'yes'
openssh__use_login: 'no'
openssh__use_privilege_separation: 'sandbox'
openssh__permit_user_environment: 'no'
openssh__compression: 'delayed'
openssh__client_alive_interval: '0'
openssh__client_alive_count_max: '3'
openssh__use_dns: 'no'
openssh__pid_file: '/var/run/sshd.pid'
openssh__max_startups: '10:30:100'
openssh__permit_tunnel: 'no'
openssh__chroot_directory: 'none'
openssh__version_addendum: 'none'

openssh__banner: 'none'

openssh__accept_env:
  - LANG
  - LC_*

openssh__subsystem: 'sftp  /usr/lib/openssh/sftp-server'
```

#### Example

```yaml
openssh__port: '22122'
openssh__banner: '/etc/ssh/banner'
```

## Example Playbook

```yaml
- hosts: all
  vars_files:
    - vars/main.yml
  roles:
     - { role: sparknsh.openssh }
```

## License

MIT

## Author Information

This role was created in 2020 by [sparknsh](https://www.sparknsh.com) at [Rebel Media, Inc.](https://www.rebelmedia.io/)

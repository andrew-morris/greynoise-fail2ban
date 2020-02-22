# Installation

- Add greynoise.conf to /etc/fail2ban/actions.d/
- Edit /etc/fail2ban/jail.conf (or jail.local) with something that looks like the following:

```
[sshd]
port    = ssh
logpath = %(sshd_log)s
backend = %(sshd_backend)s
enabled = true
mode    = aggressive

action_greynoise = greynoise

action = %(action_)s
         %(action_greynoise)s
```

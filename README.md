# Installation

- Add greynoise.conf to /etc/fail2ban/action.d/greynoise.conf
- Edit /etc/fail2ban/action.d/greynoise.conf and add your GreyNoise API key where it says "<API_KEY_GOES_HERE>"
- Edit /etc/fail2ban/jail.conf (or jail.local), make sure "[sshd]" is uncommented, and add the following lines under the "[sshd]" section:

```
action_greynoise = greynoise
action = %(action_)s
         %(action_greynoise)s
```
# FAQ

* What does this do?

Currently, not much. The first pass of this integration is simply to silently look up each IP your server bans against GreyNoise. The next pass will have more functionality. 

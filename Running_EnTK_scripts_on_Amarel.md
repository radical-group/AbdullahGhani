**If you are situated off campus you would need to install the Cisco AnyConnect VPN as Amarel only allows connection from RU-Wireless network.**

1. Make sure you have passwordless SSH access set up to connect to amarel.
 [This]( https://www.tecmint.com/ssh-passwordless-login-using-ssh-keygen-in-5-easy-steps/) link should help you with setting up password-less SSH access.
 
   Make sure you set no pass phrase. After that [this](https://linuxize.com/post/using-the-ssh-config-file/) link should help you set your username and path to your IdentityFile id_rsa respective to Amarel.
 
2. Place the config file I have in the repo in the following directory.  
`~/.radical/pilot/configs/resource_rutgers.json`

*If any of those directories do not exist, make sure you create them*

3. Change the resource description in the `entk.py` script as such
```python
# Apply the resource configuration provided by the user
    res_dict = {
        'resource': 'rutgers.amarel',
        'walltime': 10,
        'cpus': 2,
        'schema': 'local'}

    # Assign resource request description to the Application Manager
    amgr.resource_desc = res_dict
```
*You can change the cpu allocation to suit your needs.*

4. Run the EnTK script. That should be it.

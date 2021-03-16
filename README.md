# README

> The initial run does need an authorized key on the host that was placed  
> during the creation of the machine.

## Quickstart

### Set host

```shell script
HOSTNAME=nextcloud.example.com
echo "$HOSTNAME" > hosts
```

### Setup Nextcloud

A user `ansible` is created and `password` sets the password for that user.
The nextcloud admin password is set with `cloudpassword` and nextcloud
admin user is `admin-next`.

```shell script
ansible-playbook -i hosts -u root --extra-vars 'upassword=PASSWORD cloudpassword=PASSWORD' setup_nextcloud.yml
```

## Debugging

After the initial run no root login is possible. The user `ansible` has to be
used. The `upassword` variable has to be provided, even if it is not used.

```shell script
ansible-playbook -i hosts -u ansible -K --extra-vars 'upassword=' setup_nextcloud.yml
```

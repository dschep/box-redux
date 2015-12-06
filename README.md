# Ansible scripts provision a computer to my tastes

Easily setup up a machine to my liking using ansible. Should work on
recent-ish Ubuntu installs (14.04+) and upgrades Debian testing(stretch,
currently) to unstable(sid).

The included `site.yml` automatically only installs desktop packages when a GUI
is present. Customization is straightforward with well(hopefully) separated
roles.


## Quick Install

```
curl http://schep.me/box-redux/install | bash -x
```
or
```
wget -qO- http://schep.me/box-redux/install | bash -x
```

## Ways of running (after quick install or cloning)
You can obviously use a global inventory file, but often that's not
convenient so it's easier to use `-i hostname,`. It's best to use the real
hostname instead of localhost because like that the paybook can easily use
that name to decide what to install.

### Quick install
This is what the quick install runs.
```
ansible-playbook -i $HOSTNAME, site.yml
```

### Install Secrets
This installs any secrets that are encrypted with ansible-vault
```
ansible-playbook -i $HOSTNAME, --ask-vault-pass secrets.yml
```

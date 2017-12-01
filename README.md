# ansible-xmrig
Ansible Playbook to download XMRIG miner for Monero Mining from GIT source, build on all nodes and run automatically at server boot.

Currently tested on:
* Debian 9

### \*\*\*IMPORTANT BEFORE LAUNCHING \*\*\*

ALL NODES INVOLED IN MINER DEPLOYMENT WILL BE REBOOTED AT THE END OF INSTALLATION

### 1 - Configuration

Edit *configuration.yml*

`public_key` : SET YOUR XMR PUBLIC KEY

`mining_pool` : SET MONERO POOL (eg. mine.moneropool.com:3333)

`log_file` : XMRIG LOG FILE

`max_cpu_usage` : MAXIMUM CPU USAGE FOR MINING THREADS 

You can find a list of available Monero pools here:
http://moneropools.com/


### 2 - Add Hosts

Modify *hosts* file, add IP or hostnames of your nodes where you want deploy XMRIG miner.
Include in your host line the user allowed to access to the node by ssh, you can use different host users.

```
1.2.3.4  ansible_user=myuser
5.6.7.8  ansible_user=anotheruser
```

**Installation requires sudoers user with root priviliges (sudo)**

### 3 - New on Ansible? (optional)

Ansible delivers simple IT automation, it's agentless and works by SSH connections

Install Ansible on you local enviroment:

**Debian / Ubuntu**

```
apt-get install ansible
```

### 4 - Run

```
ansible-playbook -i hosts install.yml
```

### 5 - Enjoy mining!

## Troubleshooting

**Ansible Error:** */usr/bin/python: not found - "msg": "MODULE FAILURE"*

Add to your host file python3 path as ansible_python_interpreter variable value

```
1.2.3.4   ansible_user=myuser     ansible_python_interpreter=/usr/bin/python3
```





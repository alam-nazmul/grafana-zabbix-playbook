# Grafana Zabbix Ansible Playbook

![image](https://user-images.githubusercontent.com/6326478/80306541-eb755680-87fe-11ea-958e-5b2428c2bdc2.png)


Ansible playbook + Vagrantfile for provisioning [Grafana](https://grafana.com/) and [Zabbix](https://zabbix.org/wiki/Main_Page) to a CentOS server. The playbook also installs H2O, PHP and mySQL.

## Getting started

Edit `/group_vars/web.yml` and `hosts` and add your domain/hosts. Then run:

```
ansible-playbook -i hosts playbook.yml
```

* Zabbix dashboard should be running at: `YOUR_DOMAIN/zabbix`
* Grafana dashboard should be running at: `YOUR_DOMAIN/grafana`

## Zabbix Configuration

1. Install `zabbix-agent` on the servers you want to monitor. You can use `/roles/zabbix` for the installation
2. Register those servers from Configuration > hosts.

## Grafana Configuration
1. Login with ID admin/PW admin.
2. Enable zabbix-grafana plugin from plugin dashboard. Follow [the official guide](https://alexanderzobnin.github.io/grafana-zabbix/configuration/).

You should be able to build your own monitoring dashboard on grafana using zabbix server now!

## Running on VM
Simply run `vagrant up`. You'll need:
* Vagrant 1.8.6 or later
* VirtualBox 5.1.6 or later

## What's installed

- CentOS7
- PHP 7.4
- H2O latest
- mySQL v8
- Zabbix 4.4.7
- Grafana 6.7.2

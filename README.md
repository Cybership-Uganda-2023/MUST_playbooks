
# Ansible playbooks
*installing Wazuh with Ansible*

This section largely follows the [official Wazuh documentation](https://documentation.wazuh.com/current/deployment-options/deploying-with-ansible/installation-guide.html). Ansible and its clients are assumed to have been installed and configured correctly.

On the **Ansible server**, go to `/etc/ansible/roles/wazuh-ansible/playbooks/MUST_playbooks`. Execute the following commands to install the Wazuh indexer, dashboard, server and agents:

```Bash
sudo ansible-playbook MUST.wazuh-indexer-and-dashboard.yml -b -K

sudo ansible-playbook MUST.wazuh-manager.yml -b -K

sudo ansible-playbook MUST.wazuh-agents.yml -b -K

```

The following commands can be used on the relevant instances to check the installation of the indexer, dashboard, manager and agents:

```Bash
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-agent
```

The Wazuh-dashboard can now be reached internally by using the dashboard instance's private IP, at `https://<private IP>`, and exteranally by using the dashboard instance's public DNS addressn at `https://<public DNS>`. 

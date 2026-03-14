# Environment Setup

## Wazuh Server
- Ubuntu Server 24.04.4
- RAM: 4094 MB
- CPU: 2 cores
- Execution Cap: 80%
- SATA: ubuntu.vdi (25.00 GB)
- IP:192.168.56.4

Install:

## Ubuntu Server with Wazuh
) ip a (check if it is connected)
) ping 8.8.8.8
) sudo apt update
) sudo apt upgrade
) curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
) sudo bash wazuh-install.sh -a
) sudo systemctl status wazuh-manager
) sudo systemctl status filebeat
) sudo systemctl status wazuh-indexer
) sudo systemctl status wazuh-dashboard

## Windows Agent
) Install Wazuh agent 
) Open the command prompt (cmd) as administrator 
and navigate to the folder where it was installed.
) run "C:\Program Files (x86)\ossec-agent\agent-auth.exe" -m IP_SERVER (in this case 192.168.56.4)
) Ping to establish connection as active

## ArchLinux Agent
) sudo yay -S wazuh-agent
) edit /var/ossec/etc/ossec.conf
) Seach for: 
		<client>
		  <server>
		    <address>IP_SERVER</address>
		  </server>
		</client>
) Put the server ip between <address>
) sudo systemctl restart wazuh-agent
) sudo systemctl enable wazuh-agent
) sudo systemctl status wazuh-agent
) Ping to establish connection as active

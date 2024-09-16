# Installing Wazuh
There is a command to install on the Wazuh site.
```bash
curl -sO https://packages.wazuh.com/4.9/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

If `ufw` is running open up the ports 1515, 1514, and 443. It uses a **self-signed certificate**.
```bash
sudo ufw allow tcp/1515
sudo ufw allow tcp/1514
sudo ufw allow tcp/443
```

When the installation completes it will generate an admin username and password to log in to. In the interface it generates a command to set up an **agent** (client). Create another VM to be an agent.

To deploy a new agent go to server management, endpoints summary.

It will ask you some questions to generate the script.
- os and package type
- ip of the agent
- agent name (identifer)
- groups

The command generated should look like this.
```bash
wget https://packages.wazuh.com/4.x/apt/pool/main/w/wazuh-agent/wazuh-agent_4.9.0-1_amd64.deb && sudo WAZUH_MANAGER='192.168.1.228' WAZUH_AGENT_NAME='wazuhagentlinux' dpkg -i ./wazuh-agent_4.9.0-1_amd64.deb
```

It will also give you the commands to start the service within the client.
```bash
sudo systemctl daemon-reload 
sudo systemctl enable wazuh-agent 
sudo systemctl start wazuh-agent
```

Had to disable the firewall to get access and use the right IP for the server. Now it works.

Laptop does not have enough RAM to run all these VMs; Ubuntu server, Ubuntu server, Kali Linux, Windows 10. I think I get the gist of how to setup and what this is for.


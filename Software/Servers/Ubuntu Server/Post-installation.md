# Update software
```bash
sudo apt-get update -y && sudo apt-get upgrade -y;
sudo apt-get dist-upgrade -y;
sudo apt-get autoremove -y;

# reboot the server
sudo reboot now
```

# Install software
Install whatever you need on the server.
```bash
sudo apt install neovim neofetch htop git openssh-server ufw fail2ban mysql-server -y
```

# Setup services

## Setting up SSH
Configuration files are located in `/etc/ssh/sshd_config`.
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
sudo systemctl status ssh

# after making configuration changes, reload the service
sudo systemctl reload ssh
```

Make sure to exchange public keys with the server. 
```bash
ssh-copy-id -i /home/brandon/.ssh/id_pub.rsa ubuntu@192.168.1.175
```

Edit the configuration file after exchanging public keys. Keep two ssh sessions connected to the server just in case there is a mistake in the config. Disable `PasswordAuthentication` and `PermitRootLogin`

Add the IP to `/etc/hosts` so you do not have to memorize and type the IP address of the server.
## Setting up UFW
```bash
sudo systemctl enable ufw
sudo ufw enable
sudo systemctl start ufw
sudo systemctl status ufw
```

Add basic rules. Open the minimum amount of ports necessary for hosts to access your services.
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing 
sudo ufw limit 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp

# reload the service to allow changes to take effect
sudo ufw reload
```
## Setting up fail2ban

## Setting up MySQL

## Setting up PostGreSQL

## Setting up NGINX

## Setting up Apache
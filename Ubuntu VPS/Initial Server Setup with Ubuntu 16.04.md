# Initial Server Setup with Ubuntu 16.04

(https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04)  

## Firewall
`sudo ufw status`  
`sudo ufw allow from <MY_IP_ADDRESS>/32 to any port 22`  
`sudo ufw enable`  
`sudo ufw status`

(https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands)

## Software and System Maintenance
`sudo apt-get update`  
`sudo apt-get dist-upgrade`  

## Check Time Zone
`date`

## Configure SWAP
// check memory
`free -m`

// check space on hard drive
`df -h`

// create a 1 Gigabyte file
`dd if=/dev/zero of=/swapfile bs=128M count=8`

// or create a 2 Gigabyte file
`dd if=/dev/zero of=/swapfile bs=512M count=2`

// verify that 1 or 2 Gigabytes have been allocated
`ls -lh /swapfile`

// adjust permissions on swap file
`sudo chmod 600 /swapfile`

// set up the swap space
`mkswap /swapfile`

// start using the swap space
`swapon /swapfile`

// persist swap memory, open fstab
`nano /etc/fstab`

// add at end, save, reboot
`/swapfile	none	swap	sw	0	0`

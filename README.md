# dnsmasq setting in ubuntu 14.04

$ sudo nano /etc/NetworkManager/NetworkManager.conf

- search for "dns=dnsmasq"
- replace with "#dns=dnsmasq"

$ sudo apt-get install dnsmasq

$ sudo nano /etc/dnsmasq.conf

- append line: "listen-address=127.0.0.1"
- append line: "bind-interfaces"
- append line: "address=/dev/127.0.0.1"

$ sudo netstat -plant | grep :53

- look for "NUMBER/dnsmasq"

$ sudo kill -9 NUMBER

- fill in the number you found for "NUMBER"

$ sudo service dnsmasq restart

$ sudo nano /etc/dhcp/dhclient.conf

- append line: "prepend domain-name-servers 127.0.0.1;"

$ sudo service network-manager restart

source : https://www.leaseweb.com/labs/2013/08/wildcard-dns-ubuntu-hosts-file-using-dnsmasq/

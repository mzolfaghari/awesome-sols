
## Noisy Fan!

#### Problem: Controle the speed of fan: 
Using the following package (works on both linux and windows):

https://github.com/hirschmann/nbfc



#### Problem: systemd-resolve high cpu usage: 
check by 'top' or 'atop' to find out which application wastes your CPU! If it's 'systemd-resolve' then the following solutions might help:

##### Solution 1:
 add `DNSStubListener=no` in `/etc/systemd/resolved.conf` and then `sudo service systemd-resolved restart`.

##### Solution 2:
Add the line `DNSMASQ_EXCEPT=lo` to `/etc/default/dnsmasq`

`sudoedit /etc/default/dnsmasq`
Restart dnsmasq via

`sudo service systemd-resolved restart`

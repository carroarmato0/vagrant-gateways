# vagrant-gateways
Vagrant File for spawning Centos 7 based gateways

I sometimes want to test PFSense and OPNSense Multi Wan setups.

This setup allows you to specify how many instances you want and uses Ansible to take care of the rest.

## What you get

- Centos 7
- 512MB Ram
- eth0: NAT, eth1: private internal network
- dhcpd
- Google public DNS (8.8.8.8, 8.8.4.4)
- Per instance, a private internal network is created with 192.168.**x**00.0/24 called gw**x**_lan

## How do I use this?

1. Have VirtualBox (tested on 5.2.22)
2. Have Vagrant (tested on 2.2.2)
3. Have Ansible (tested on 2.7.5)
4. Git clone this repo
```
git clone https://github.com/carroarmato0/vagrant-gateways.git
```
5. (Optional) Customize how many instances you want by editing the Vagrantfile
```
(1..2).each do |i|
```
6. Fire up the instances
```
vagrant up
```
7. In the Network settings of the VM you want patch through to your Gateways, you just need to select **Network > Adaptor 1 > Attached to: Internal Network, Name: gwx_lan**

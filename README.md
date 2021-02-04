# Test a cloud-init locally

If you want to validate a cloud-init file locally or without spinning up a real VM on the cloud, then the most suitable choice  is Vagrant.



### Prerequisites

- [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
- [VirtualBox Extension Pack](https://download.virtualbox.org/virtualbox/6.1.18/Oracle_VM_VirtualBox_Extension_Pack-6.1.18.vbox-extpack)
- [Vagrant](https://www.vagrantup.com/downloads)



### Getting started

###### Install vagrant plugins

```bash
vagrant plugin install vagrant-disksize && vagrant plugin install vagrant-env
```



###### Clone repo

```bash
git clone git@github.com:tankibaj/Cloud-init-Vagrant.git && cd Cloud-init-Vagrant
```



###### Modify user-data.yml (optional)

```bash
nano user-data.yml 
```



###### Spin up a VM

```bash
vagrant up
```


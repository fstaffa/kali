# packer-kali

Copied from: https://github.com/chrisanthropic/packer-kali
A Kali 2018-3 build for Packer

## Requirements

- Packer
- Vagrant
- Virtualbox and/or VMware

## About the Boxes

#### Kali linux rolling

#### Metasploitable 2

Download [Metasploitable 2](http://sourceforge.net/projects/metasploitable/files/Metasploitable2/metasploitable-linux-2.0.0.zip/download) from Sourceforge. Unpack the file `Metasploiable2.vmdk` into the directory `packer/metasploitable/`.

Build using [packer](https://packer.io):

    $(cd packer/kali; packer build kali-2-amd64.json)
    $(cd packer/metasploitable; packer build metasploitable2.json)
    $(cd packer/debian-lenny; packer build debian-lenny-5.0.10-amd64-netinst.json)
    $(cd packer/damn-vulnerable-node-application; packer build dvna-ubuntu-15.10-amd64.json)

## Use

##### Packer

Create the box you want (either virtualbox or vmware)

- git clone https://github.com/ctarwater/packer-kali.git
- cd packer-kali
  - virtualbox: packer build -only=virtualbox-iso kali.json
  - vmware: packer build -only=vmware-iso kali.json

##### Vagrant

Use the provided Vagrantfile.

- change `kali.vm.box = "blackfin/kali"` to `kali.vm.box = "location/of/local/box"` to use your own rather than the one we offer on VagrantCloud
- cd to /packer-kali
  - virtualbox: vagrant up --provider=virtualbox
  - vmware: vagrant up --provider=vmware_desktop

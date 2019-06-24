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

Build using [packer](https://packer.io) and add to vagrant

```
cd packer/kali
packer build kali.json
vagrant box add --name kalirolling-2019-2 builds/virtualbox-kali.box

cd packer/metasploitable; packer build metasploitable2.json
```

## Use

##### Packer

Create the box you want (either virtualbox or vmware)

- git clone https://github.com/ctarwater/packer-kali.git
- cd packer-kali
  - virtualbox: packer build -only=virtualbox-iso kali.json
  - vmware: packer build -only=vmware-iso kali.json

##### Vagrant

Use the provided Vagrantfile.



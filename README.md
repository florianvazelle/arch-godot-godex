## Install requirements

```
sudo apt install virtualbox packer vagrant
```

## Create a Arch Linux base box

```
cd packer-arch/
packer build -only=virtualbox-iso arch-template.json
vagrant box add arch output/packer_arch_virtualbox-2022.07.01.box
```

## Setup Godot with Godex

```
cd ..
mkdir data
cd data/godot
git apply ../godex/patches/add_custom_iterator.patch --reject --ignore-space-change --ignore-whitespace
```

## Run VM

```
cd ../..
vagrant up --provision
```

## In VM

```
cd /vagrant_data/godot
./bin/godot.linuxbsd.tools.64
```
## Install requirements

```
sudo apt install virtualbox vagrant
```

## Create an Arch Linux base box

```
cd packer-arch/
packer build -only=virtualbox-iso arch-template.json
vagrant box add arch output/packer_arch_virtualbox-2022.07.01.box
cd ..
```

## Setup Godot with Godex

```
mkdir -p data
cd data/godot
git apply ../godex/patches/add_custom_iterator.patch --reject --ignore-space-change --ignore-whitespace
cd ../..
```

## Run VM

```
vagrant up --provision
```

## In VM

```
cd /vagrant_data/godot
./bin/godot.linuxbsd.tools.64
```
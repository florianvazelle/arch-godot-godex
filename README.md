## Install requirements

```
sudo apt install virtualbox vagrant packer
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
cd data/godot
git apply ../godex/patches/add_custom_iterator.patch --reject --ignore-space-change --ignore-whitespace
cd ../..
```

## Run VM

```
vagrant up --provision
```

## In VM

Login with credential `vagrant/vagrant`, and run:
```
cd /vagrant_data
./build.sh
./run.sh
```
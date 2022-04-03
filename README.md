# vagrant-vms

This repo contains Vagrantfiles that can be used to quickly create
one or multiple virtual machines that later can be used as a test 
environments.

## When to use?

It is ideal for you when you have to quickly create a test environment on
your local machine. I would rather not use it on a production, unless you
want to use it as a base.

## How to use?
- Just create a virtual machine with a default configuration
```sh
# pattern
# cd <provider-name>
# vagrant up --provision

# an example
cd virtualbox
vagrant up --provision
```
- Use specific config file
```sh
# pattern
# cd <provider-name>
# CONFIG_FILE=<path-to-config-file> vagrant up --provision

# an example
cd virtualbox
CONFIG_FILE=config/centos7/one-clean-machine.yaml vagrant up --provision
```

- Create custom config file
```sh
# create an yaml file under the ./<provider>/config/ directory
# with a content like in a default one. All fields in 
# <provider>/config/default.yaml are mandatory!
# 
# If you want to create more than one vm, simply add another
# vm definition to the `machines` list. An example of this 
# can be found in <provider>/config/centos7/two-clean-machines.yaml
```

- Destroy environment
```
vagrant destroy -f
```

## Description

Project structure
```sh
|- provider-one
|--| Vagrantfile
|--| config
|--|--| default.yaml
|--|--| ...
|--| provisioning
|--|--| shell
|--|--|
|--|--| ansible
|--|--|

```

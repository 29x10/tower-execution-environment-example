# tower-execution-environment-example

This is an example to setup ansible controller that run againest windows host with winRM and kerberos authentication

A few steps needed for certain environment

1. update krb5.conf file to your own KDC REALM
2. update container image base image
    1. search available images https://catalog.redhat.com/software/containers/search?p=1&q=ansible-builder-rhel8
    2. search available imasge https://catalog.redhat.com/software/containers/search?p=1&q=ee-minimal-rhel8
    3. check python version to update bindep.txt file, for 22 we use python39


## Setup

```
python -m pip install pdm --user
python -m pdm install
```

## How to create container file

```
python -m pdm run ansible-builder create
```

## How to build

```
python -m pdm run ansible-builder build --no-cache -v 3 -t ansible-execution-env:latest
```

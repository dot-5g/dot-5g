# Getting Started

In this tutorial we will deploy dot-5g on a single machine using Juju. We will also deploy a radio simulator that will be used to test the 5G network. This tutorial assumes you are running Ubuntu 22.04 LTS. It should work on Operating Systems, but you may need to install some dependencies differently.

## Install Dependencies

First open a terminal and install `Juju`, `MicroK8s` and `Kubectl`:


```bash
snap install microk8s --classic
snap install kubectl --classic
snap install juju --classic
```

Then enable the `dns` and `storage` MicroK8s plugins:

```bash
microk8s.enable dns storage
```

## Boostrap a Juju controller

Next, bootstrap a Juju controller:

```bash
juju bootstrap microk8s localhost
```

Create a model for dot-5g:

```bash
juju add-model dot-5g
```

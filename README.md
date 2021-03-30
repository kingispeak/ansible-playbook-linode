# ansible-playbook-linode

![ansible-lint workflow](https://github.com/kingispeak/ansible-playbook-linode/actions/workflows/ansible-lint.yml/badge.svg)

An ansible playbook to provision a new linode and give it a hostname and a FQDN, deploys a public ssh key under its root account and disable password based ssh login.

# Getting started

The default creates a Linode 1024 in Tokyo 2, JP.
It gives installs Ubuntu 20.04 LTS.

## Installation

`pip3 install linode_api4`

## Usage:

Create a `.vault_pass` file containing a strong password in the project root

      openssl rand -base64 64 > .vault_pass
      cp vars.example vars
      ansible-vault encrypt vars

Update vars file and run playbook

      ansible-playbook --extra-vars hostname=<your_hostname> provision.yml

# Ansible Role: Vim

[![Build Status](https://travis-ci.com/mattladany/ansible-role-vim.svg?branch=master)](https://travis-ci.com/mattladany/ansible-role-vim)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://raw.githubusercontent.com/mattladany/ansible-role-vim/master/LICENSE)

Installs the latest [Vim](https://github.com/vim/vim) release from source on Ubuntu16.04/Centos7 operating systems.

**Note:** Many of the steps and packages that get installed by this role were taken from this [YouCompleteMe](https://github.com/Valloric/YouCompleteMe/wiki/Building-Vim-from-source) wiki. 

## Requirements

None

## Role Variables

None

## Dependencies

None

## Example Playbook

```
- hosts: servers
    roles:
      - { role: mattldany.vim }
```

## License

MIT

## Author Information

This role was created by Matt Ladany.

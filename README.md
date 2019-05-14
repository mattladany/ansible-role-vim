# Ansible Role: Vim

[![Build Status](https://travis-ci.com/mattladany/ansible-role-vim.svg?branch=master)](https://travis-ci.com/mattladany/ansible-role-vim)
[![role](https://img.shields.io/ansible/role/39137.svg)](https://galaxy.ansible.com/mattladany/vim)
[![license](https://img.shields.io/badge/License-MIT-blue.svg)](https://raw.githubusercontent.com/mattladany/ansible-role-vim/master/LICENSE)

Installs the latest (or specified) [vim](https://www.vim.org/) 'release' from source on Ubuntu16.04 and Centos7 systems.

There are many plugins for vim that require a version of vim greater than 8.0, but most repos for Debian/RedHat systems only come with 7.4. This ansible role attempts to solve this problem by reliably compiling and installing vim from the vim Github repository. There exists other installation guidelines (i.e., this [Valloric/YouCompleteMe](https://github.com/Valloric/YouCompleteMe/wiki/Building-Vim-from-source) Github wiki); however, I have found that these instructions provide solutions that are too broad and confusing for users that desire a more customized build. Using this ansible role will provide the ability to:

- Choose your desired version of vim
- Compile vim with the dependencies that you need
- Elegantly install vim on any operating system _[In Progress]_

## Requirements

The requirements to compile vim from source are highly dependent upon simply what you want vim compiled with. Currently, this role compiles vim with all possible options, and installs all the requirements for you:

- git
- lua
- python3
- ruby
- perl

For a full list, see ```_vim_dependencies``` in [vars](https://github.com/mattladany/ansible-role-vim/tree/master/vars)/OS.yml for your operating system.

## Role Variables

Available variables are listed below, along with their default values (see ```defaults/main.yml```):

```vim_version: v8.1.1330```

Set this to the version of vim you would like to install. The default will continually get more up-to-date as this role has new releases. See [here](https://github.com/vim/vim/releases) for a list of the latest vim releases.

```vim_tarball_url: https://github.com/vim/vim/tarball/{{ vim_version }}```

The url to download the vim tarball from.

```vim_latest: false```

Whether the latest version of vim should be found and installed, or if the specified version should be used.

**IMPORTANT:** getting the latest version may have unreliable results without pairing an SSH key with Github, since Github blocks too many requests from the same IP address without one (this is why many of my early travis-ci tests failed). See [here](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) for how to set up a new SSH key with Github.

```vim_download_dir: /usr/local/src```

Where the tarball should be downloaded to.

```vim_src_dir: {{ vim_download_dir }}/vim```

Where the tarball should be untar'd to.

```vim_runtime_dir: /usr/local/share/vim/vim81```

Should not be changed unless you want a vim version older than 8.1.

## Dependencies

None

## Example Playbooks

### Installing a specific version

```
- hosts: servers
  become: yes
  roles:
    - { role: mattladany.vim, vim_version: v8.1.1330 }
```

### Installing the latest version

```
- hosts: servers
  become: yes
  roles:
    - { role: mattladany.vim, latest: yes }
```

## License

[MIT](https://raw.githubusercontent.com/mattladany/ansible-role-vim/master/LICENSE)

## Author Information

This role was created by Matt Ladany.

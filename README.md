# Ansible Playbook for Ubuntu

This playbook is made to automate the installation and configuration of an Ubuntu
machine for personal use.

## Requirements

Install Ansible on your machine:

```bash
sudo apt install ansible
```

## Project Structure

The main script is [`installer.yml`](installer.yml) which is the entry point for the
ansible playbook. This script has four main steps:

1. Install dependencies: installs basic dependencies for Ubuntu, some git tools and configures
fish shell and kitty terminal.
2. Download applications: installs desktop applications such as Google Chrome, Jetbrains Toolbox or Postman
3. Setup dotfiles: clones my [dotfiles repository](https://github.com/dimanu-py/dotfiles), substitutes all
the configuration files using `stow` and sets up `pyenv`.
4. Wallpaper: sets the wallpaper to a custom one.

## Usage

You can run the complete playbook with the following command:

```bash
ansible-playbook -K -i inventory.ini installer.yml
```

Alternatively, you can run each step separately using the tags that 
are defined in the [`installer.yml`](installer.yml) file.

```bash
ansible-playbook -K -i inventory.ini installer.yml --tags "tag_name"
```



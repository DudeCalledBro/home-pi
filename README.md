# Home Pi

[![CI](https://github.com/DudeCalledBro/home-pi/actions/workflows/ci.yml/badge.svg)](https://github.com/DudeCalledBro/home-pi/actions/workflows/ci.yml)

This repository contains the Ansible code for my Home-Pi project. The Home-Pi runs various services for home automation as well as other useful utilities. The Ansible playbooks and roles in this repository automate the setup and configuration of these services, ensuring a consistent and easily reproducible environment.

## Prerequisites

- Ensure you have Ansible installed (e.g. `pip3 install ansible`)
- Ensure Docker is installed (you may want to checkout my [ansible-docker-role](https://github.com/DudeCalledBro/ansible-role-docker))

## Setup

Follow these steps to set up your automated Home Assistant deployment:

### Setting Up Your Inventory

1. Navigate to the inventories directory:

    ```bash
    cd inventories
    ```

2. Create a copy of the example hosts file:

    ```bash
    cp example.hosts.yml hosts.yml
    ```

3. Customize the `hosts.yml` file to match your homelab setup:

    ```bash
    vim hosts.yml
    ```

    Customize the file according to your network layout. For example:

    ```yaml
    all:
      hosts:
        server1:
          ansible_host: 192.168.1.10
    ```

    **Important:** If you need to fine-tune specific settings for your Home Assistant deployment, consider overriding default role variables in the group or host-specific variable files. This allows precise configuration of your setup.

4. Run the Ansible playbook to deploy Home Assistant:

    ```bash
    ansible-playbook play-homeassistant.yml
    ```

## License

Copyright © 2025 Niclas Spreng

Licensed under the [MIT license](LICENSE).

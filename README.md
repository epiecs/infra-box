# Infra Box

This is a ansible script to setup some basic infra that can be used in a lab:

- docker
    - management via dockge
- nginx proxy manager
- pihole for local dns
- phpipam

## Requirements

- Any host with a debian/ubuntu based OS. This has been tested on a RPI4 4GB

## Installation

1. Prepare a host with a fixed ip. Make sure that you have a user that has sudo permissions on this box.

2. Then install some needed packages

    ```bash
    sudo apt install git python3 python3-pip python3-venv python3-wheel python3-setuptools sshpass -y
    ```

3. Clone this repository

    ```bash
    git clone https://github.com/epiecs/infra-box.git
    cd infra-box
    ```

4. Initialize and use a virtual environment
    
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

5. Go to the folder and install the needed python dependencies

    ```bash
    pip install -r requirements.txt
    ```

6. Make copies of the following files and customize them to your liking:
    - `inventory.ini.example` to `inventory.ini` 
        - (replace IP address with your hosts IP, or comment that line and uncomment the `connection=local` line if you're running it on the host you're setting up).
    - `config.yml.example` to `config.yml`

7. Check `config.yml` and update this to your liking

8. Run the playbook: `ansible-playbook main.yml` - this will take a while (10-15m on a rpi4)

9. Point your dns the ip of your box - or update your hosts file

10. You can now use the following resources

    ```
    dockge.infra.box
    librenms.infra.box
    phpipam.infra.box
    pihole.infra.box/admin
    tftp.infra.box -> only on port 69 with the tftp protocol
    traefik.infra.box:8080
    ```
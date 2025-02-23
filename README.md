# Infra Box

This is a ansible script to setup some basic infra that can be used in a lab:

- phpipam

> **NOTE** I know that this is not the best way to use uv. If you are familiar with the tooling you will know how to do this more efficiently :)

## Installation

1. Prepare a host with a fixed ip. Make sure that you have a user that has sudo permissions on this box.

2. Then install some needed packages

    ```bash
    sudo apt install git python3 python3-pip python3-venv python3-wheel python3-setuptools sshpass -y
    ```

3. Clone this repository
4. Initialize and use a virtual environment
5. Go to the folder and install the needed python dependencies

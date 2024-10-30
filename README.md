# rapid7_client
Ansible - install UCL rapid7 client on Linux systems

Target limited to localhost
requires sudo access

Dependency:
  - ansible-core
  - git

Intended target systems:
  - RHEL => 8
  - Ubuntu => 22.04
  - x86_64
  - arm64 #not tested

Install dependencies if not already installed.
RHEL
sudo dnf install git ansible-core
Ubuntu
sudo apt install git ansible-core

Clone the repository
git clone https://github.com/ucl-isd/rapid7_client.git
cd rapid7_client
#run the playbook, you logged on as an account with sudo access
ansible-playbook rapid7-install.yml -K
#after install tidy up
cd ..
rm -rf rapid7_client

Alternative install
git clone https://github.com/ucl-isd/rapid7_client.git
cd rapid7_client/roles/rapid7/files/
sudo bash agent_installer-x86_64.sh install_start --token eu:1cac4914-27fe-4ab1-9fe0-74270d1c1c18"

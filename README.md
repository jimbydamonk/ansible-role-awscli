# Ansible Role: christiangda.awscli

[![Build Status](https://travis-ci.org/christiangda/ansible-role-awscli.svg?branch=master)](https://travis-ci.org/christiangda/ansible-role-awscli)
[![Ansible Role](https://img.shields.io/ansible/role/40514.svg)](https://galaxy.ansible.com/christiangda/awscli)

This role [Install AWS Command Line Interface (awscli)](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)

**Features:**
* Installed using pip
* ~~Allow configure profile (config and credentials)~~

## Requirements

This role work on RedHat, CentOS, Debian and Ubuntu distributions

* RedHat
  * 6
  * 7
  * 8
* CentOS
  * 6
  * 7
  * 8
* Ubuntu
  * 14.*
  * 16.*
  * 18.*
  * 19.*
* Debian
  * jessie (8)
  * stretch (9)
  * buster (10)
  * sid (inestable)

To see the compatibility matrix of Python vs. Ansible see the project [Travis-CI build matrix](https://travis-ci.org/christiangda/ansible-role-awscli)

## Role Variables

None

## Dependencies

* [christiangda.epel_repo](https://galaxy.ansible.com/christiangda/epel_repo) imported dynamically in the code when is used with Red Hat family, so you don't need to add this to your ansible playbook.

## Example Playbook

### RedHat/CentOS, Ubuntu and Debian

**Reading config file from JSON configuration file**

```yaml
- hosts: servers
    gather_facts: True
    roles:
      - role: christiangda.awscli
```

## Development / Contributing

This role is tested using [Molecule](https://molecule.readthedocs.io/en/latest/) and was developed using
[Python Virtual Environments](https://docs.python.org/3/tutorial/venv.html)

**Prepare your environment**

**Python 3**

```bash
mkdir ansible-roles
cd ansible-roles/

python3 -m venv venv
source venv/bin/activate
pip install pip --upgrade
pip install ansible
pip install molecule">=2.22rc1"
pip install molecule[vagrant]
pip install selinux
pip install docker
pip install pytest
pip install pytest-mock
pip install pylint
pip install rope
pip install autopep8
pip install yamllint
pip install flake8
```

**Python 2.7**

Dependencies

```bash
sudo dnf install redhat-rpm-config
sudo dnf install python-devel
sudo dnf install libselinux-python
```

```bash
mkdir ansible-roles
cd ansible-roles/

python2.7 -m virtualenv venv
source venv/bin/activate
pip install pip --upgrade
pip install ansible
pip install molecule">=2.22rc1"
pip install molecule[vagrant]
pip install selinux
pip install docker
pip install pytest
pip install pytest-mock
pip install pylint
pip install rope
pip install autopep8
pip install yamllint
pip install flake8
```

**Clone the role repository and create symbolic link**

```bash
git clone https://github.com/christiangda/ansible-role-awscli.git
ln -s ansible-role-awscli christiangda.awscli
cd christiangda.awscli
```

**Execute the test**

Using docker in local

```bash
molecule test [--scenario-name default]
```

Using vagrant in local

```bash
molecule create --scenario-name vagrant
molecule converge --scenario-name vagrant
molecule verify --scenario-name vagrant
```

or

```bash
molecule test --scenario-name vagrant
```

**Additionally if you want to test it using VMs, I have a very nice [ansible-playground project](https://github.com/christiangda/ansible-playground) that use Vagrant and VirtualBox, try it!.**

## License

This module is released under the GNU General Public License Version 3:

* [http://www.gnu.org/licenses/gpl-3.0-standalone.html](http://www.gnu.org/licenses/gpl-3.0-standalone.html)

## Author Information

* [Christian González Di Antonio](https://github.com/christiangda)

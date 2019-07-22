Ansible Virtualization Collection
=================================

[Ansible Galaxy Collection: Virtualization](https://galaxy.ansible.com/crivetimihai/Virtualization):

- KVM
- VirtualBox
- VMware Workstation
- LXC/LXD
- Docker-CE
- Podman (with Buildah and Skopeo)

Tested on:
----------

- CentOS 7
- RHEL 8
- Fedora 30
- Ubuntu 18.04
- Debian 10

Example
-------

### Install the role:

```bash
pip install --upgrade mazer
mazer install crivetimihai.virtualization
```


### playbook.yml example

```yaml
# ansible-playbook -i localhost, playbook.yml -e "vmware_workstation_license_key='XXXXX-XX...'"

- name: setup a virtualization environment
  hosts: all
  connection: local
  become: yes
  gather_facts: yes
  roles:
    - role: crivetimihai.virtualization.kvm
    - role: crivetimihai.virtualization.lxd
    - role: crivetimihai.virtualization.vmware_workstation
    - role: crivetimihai.virtualization.virtualbox
    - role: crivetimihai.virtualization.podman
    - role: crivetimihai.virtualization.docker_ce
```


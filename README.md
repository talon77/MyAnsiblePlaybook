# MyAnsiblePlaybook

This playbook contains the steps to get a basic server setup on a VM or physical server running Debian.

Ensure on your local machine you have the ansible package installed. Download both files into the same directory as the smb.conf will be copied from there to your server.

---

_Example usage when running_:
```
ansible-playbook AnsiblePlayBookDebianServerPodmanSetup.yaml -i "192.168.3.17," -u root --ask-pass
```

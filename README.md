# MyAnsiblePlaybook

This playbook contains the steps to get a basic server setup on a VM or physical server running Debian.

Ensure on your local machine you have the ansible package installed. Download both files into the same directory as the smb.conf will be copied from there to your server.

---

_Example usage when running_:
```
ansible-playbook AnsiblePlayBookDebianServerPodmanSetup.yaml -i "192.168.3.17," -u root --ask-pass
```
Another example to pull a youtube video down
```
podman run --pull always -i --rm -v "$(pwd)":/data w33ble/youtube-dl youtube-dl -f 'bestvideo[ext=mp4][height<=480]+bestaudio[ext=m4a]/best[ext=mp4][height<=480]' -o "%(title)s.mp4" https://www.youtube.com/watch?v=xxxx
```

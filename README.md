# MyAnsiblePlaybook

This playbook contains the steps to get a basic server setup on a VM or physical server running Debian.

Noteworthy Packages:

+ Cockpit ---- Web interface to manage server
+ NCDU    ---- CLI to view where and what is using up all the drive space
+ Rclone  ---- Allows mounting of cloud storage
+ Podman  ---- Docker Alternative

Podman containers that will be installed:

+ QBittorrent ---- Torrent server
+ Heimdall    ---- A local web page containg links to services that I'm running (Being replaced by Dashy)
+ Dashy       ---- This is replacing Heimdall because a config file can be used to auto load links where Heimdall can't do this
+ Gogs        ---- My own local GIT repo server
+ Samba       ---- Samba share to allow me to share content that is downloaded via QBittorrent
+ PiHole      ---- DNS filtering to block spam and other bad sites
+ TailScale   ---- VPN Mesh Network

Ensure on your local machine you have the ansible package installed. Download both files into the same directory as the smb.conf will be copied from there to your server.

---

_Example usage when running_:
```
ansible-playbook AnsiblePlayBookDebianServerPodmanSetup.yaml -i "192.168.3.17," -u root --ask-pass
```
```
ansible-playbook AnsiblePlayBookDebianServerPodmanSetup.yaml -i "192.168.3.17," -u root --ask-pass --ask-vault-pass
```
Added a "secrets.yml" ansible-vault to contain the TailScale key "TS_KEY" that the playbook uses when setting up the containers

Another example to pull a youtube video down
```
podman run --pull always -i --rm -v "$(pwd)":/data w33ble/youtube-dl youtube-dl -f 'bestvideo[ext=mp4][height<=480]+bestaudio[ext=m4a]/best[ext=mp4][height<=480]' -o "%(title)s.mp4" https://www.youtube.com/watch?v=xxxx
```
When running PiHole a great website to get block lists from is https://firebog.net/

Installing xrdp in Fedora 35
From - https://www.server-world.info/en/note?os=Fedora_35&p=desktop&f=7

First install xrdp and tigervnc-server.
```
  sudo dnf install -y xrdp tigervnc-server
```

Next start the xrdp service
```
  sudo systemctl enable --now xrdp
```
In Fedora 35, all ports are open in the firewall. If you have not changed firewall ports then the next two steps are not necessary.
```
  firewall-cmd --add-port=3389/tcp
```
```
  firewall-cmd --runtime-to-permanent
```
This last step is not mentioned in the linked instructions above but is necessary. Run this from the account of the user who will be using RDP to access the server.
```
  vncpasswd
```
Now from Windows or MacOS, access your Linux desktop using the RDP client.

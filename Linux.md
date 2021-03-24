# Linux
### Commands
Add user `herpyderpy` to `humpydumpy` group:
* ```bash
	sudo usermod -a -G herpyderpy humpydumpy```
Show groups:
* ```bash
	groups```
Another command to show groups:
* ```bash
	sudo less /etc/group```
Show users:
* ```bash
	sudo cat /etc/shadow```
Create group `herpyderpy`:
* ```bash
	sudo addgroup herpyderpy ```
Unpack `new.tar` archive to the `new` folder:
* ```bash
	tar -C new -xvf new.tar```
Show the content of the `new.tar` archive:
* ```bash
	tar -tvf new.tar```
Unpack a content of the `new.tar` archive to the current folder:
* ```bash
	tar -xf new.tar```
Create an archive `new.tar` with these `.html` files:
* ```bash
	tar -cf new.tar hardware_info.html index.html```
Show cdrom and disk info:
* ```bash
	sudo lshw -class disk```
Save the `lshw` command info to the `.html` file:
* ```bash
	sudo lshw -html > hardware_info.html```
Show current processes:
* ```bash
	ps aux```
Show current processes of the `user` user:
* ```bash
	ps aux | grep user```
Show the current disk usage (-h: human readable form):
* ```bash
	df -h```
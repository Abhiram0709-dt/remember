# remember
cs:
1)android:
cd C:\Users\Admin\AppData\Local\Android\Sdk\emulator
emulator -list-avds
emulator -avd Pixel_9 -http-proxy http://10.0.2.2:8080
cd C:\Users\Admin\AppData\Local\Android\Sdk\platform-tools
adb shell settings put global http_proxy 10.0.2.2:8080
next go to burpsuit:
in proxy settings under proxy listeners  edit -> select all interfaces and then turn intercept on in proxy
now in mobile: example.com ->burpsuit sees the http history(req) and res.
options/proxy settings->import/export CA certificate->Certificate in DER format->select file-> Downloads->give name as burpcer.der
Local\Android\Sdk\platform-tools>adb push C:\Users\Admin\Downloads\burpcer.cer /sdcard/Download/
2)Testing Iot device Security (default passwords and ports)
docker run -d -p 8090:3000 --name juiceshop bkimminich/juice-shop and open the browser localhost:8090
ipconfig (copy ip4 address)
in kali linux: nmap -sV 192.168.0.148 
run the website (login using ' OR 1=1 -- - , open network tab and see the xhr)
3)creating and analyzing disk image using dc3dd and autopsy
in kali linux: echo "Cybersecurity Lab Evidence" > evidence.txt
lsblk
sudo apt Install dc3dd
disk image created: dd if=/dev/zero of=practice_disk.dd bs=1M count=100
mount the disk: mkfs.ext4 practice_disk.dd
to verify: ls -lh practice_disk.dd
sudo autopsy and open the website and add the case
4)log file analysis for incident detection lab
cd /var/log ,last 
journalctl | less
journalctl | grep "Failed"   journalctl | grep ssh   journalctl | grep -i error
cd /var/log/apache2 ls
grep "404" /var/log/apache2/access.log  sudo journalctl -f
user(you) logs:/usr/bin/journalctl -f
see multiple login fails :
sudo apt install openssh-server -y
sudo service ssh start
ssh fakeuser@localhost then journalctl | grep "Failed password"

5)network forensics using wireshark
open wireshark with eth()  (wireshark &)
apply filters: tcp  	ip.addr == 192.168.0.161  Ip.src== 192.168.0.161
right click on a packet and click on follow tcp stream 
to see windows packets:
nmap –sS 192.168.0.156   (use your windows ip)
filter: tcp.flags.syn == 1 && tcp.flags.ack == 0
explore wiresharks statistics 

6)audit popular apps like whatsapp and facebook
sudo apt update  sudo apt install nodejs npm –y
sudo npm install -g nativefier
nativefier https://web.whatsapp.com
cd WhatsAppWeb-linux-x64 
./WhatsAppWeb
1.	Open browser in Kali 
2.	Go to: https://reports.exodus-privacy.eu.org 
start wireshark , observe whatsapp packets use tls and dns filters 
audit facebook using bursuit

7)conducting security audit and risk assessment
windows+R msinfo32
settings -> windows update
Windows Defender Firewall
windows security ->virus 
check password:Settings → Accounts → Sign-in options
check installed apps, startup apps
settings -> network and internet
chrome ->Safe browsing
backup settings
STEP 11: Risk Assessment Table

Asset	Threat	Vulnerability	Risk Level	Solution
Personal Files	Data Loss	No Backup	High	Enable OneDrive
System	Malware	Unknown Apps	High	Remove apps
Network	Hacking	Public Network	Medium	Use Private
Account	Unauthorized Access	Weak Password	High	Strong password

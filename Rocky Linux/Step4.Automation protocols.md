**automation script<br>
자동화 스크립트<br>

<br>
<br>
<br>

*Telnet<br>

![image break](../Pictur/step4/tel1.png)<br>



#!/bin/bash<br>
dnf -y install telnet-server<br>
dnf -y install telnet-clients<br>
firewall-cmd --add-service=telnet<br>
systemctl --now enable telnet.socket<br>

firewall-cmd --permanent --add-service=telnet<br>
firewall-cmd --reload<br>
<br>
<br>

*FTP

![image break](../Pictur/step4/ftp1.png)<br>


#!/bin/bash<br>
dnf -y install vsftpd<br>
dnf -y install ftp<br>
firewall-cmd --add-service=ftp<br>
systemctl --now enable vsftpd<br>

firewall-cmd --permanent --add-service=ftp<br>
firewall-cmd --reload<br>
<br>
<br>


*SSH

![image break](../Pictur/step4/ssh1.png)<br>


#!/bin/bash<br>
dnf -y install openssh-server<br>
dnf -y install openssh-clients<br>
firewall-cmd --add-service=ssh<br>
systemctl --now enable sshd<br>

firewall-cmd --permanent --add-service=ssh<br>
firewall-cmd --reload<br>


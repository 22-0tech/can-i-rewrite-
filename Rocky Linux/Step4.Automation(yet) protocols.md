







명령어 연속 실행
dnf -y install telnet-server; systemctl --now enable telnet.socket; firewall-cmd --add-service=telnet





setup_ftp.sh

#!/bin/bash
dnf -y install vsftpd
systemctl --now enable vsftpd
firewall-cmd --add-service=ftp

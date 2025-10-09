init → systemd (슈퍼 데몬)

예전엔 init이 런레벨 기반으로 시스템을 구동했지만
지금은 systemd가 **서비스(데몬)**를 관리하는 핵심 프로세스입니다.

즉, systemd는 모든 데몬(sshd, crond, quota 등)을 관리하는 "슈퍼 데몬"입니다.

→ systemctl start quotaon.service 같은 식으로 쿼터도 systemd에서 관리 가능

MBR → 부트 로더
GRUB 부트 로더
부트로더 → 리눅스 커널을 메모리에 적재

PID 1번
프로그램 일련번호 1번
systemd

RHEL 6 → RHEL 7
init → systemd

vi /etc/inittab

init + 런레벨 = 시스템 상태 즉시 변경

런레벨 2, 3, 4 → CLI 모드, 다중 사용자 모드



vi /etc/grub.d/00_header
cat << EOF
set superusers="mylinux"
password mylinux 1234
EOF

적용
grub2-mkconfig -o /boot/grub2/grub.cfg


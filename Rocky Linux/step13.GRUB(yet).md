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


데몬(daemon)

sshd, crond, httpd, atd, quotaon 등은 모두 백그라운드 서비스

이 중 쿼터 관련 서비스는 디스크 사용을 주기적으로 감시하고 제한

→ 즉, quota 데몬(서비스) 도 systemd가 관리하는 하나의 데몬


소켓/inetd 방식 vs 독자형(standalone)

quota는 독자형(standalone) 방식 → 부팅 시 바로 활성화됨

telnet처럼 inetd(socket) 방식은 요청 있을 때만 실행

→ 즉, 쿼터는 항상 시스템이 켜져 있을 때 상시 감시하는 서비스


5️⃣ sync (디스크 저장)

시스템 종료 시 메모리의 변경 내용을 디스크로 동기화

쿼터 역시 디스크 사용량 정보(aquota.user)를 파일로 저장하므로
sync는 쿼터 데이터 손실 방지 역할도 함

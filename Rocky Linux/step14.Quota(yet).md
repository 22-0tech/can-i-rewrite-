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







vi /etc/fstab 

(defaults,usrjquota=aquota.user,jqfmt=vfsv0  1  2)
usrjquota=aquota.user → 사용자 쿼터 파일 이름 지정

jqfmt=vfsv0 → 쿼터 포맷 지정 (Linux용 최신 형식)

/etc/fstab에 위 옵션을 추가해야 쿼터 기능이 활성화됨




UUID=xxxx-xxxx  /home  ext4  defaults  1  2

UUID=xxxx-xxxx  /home  ext4  defaults,usrjquota=aquota.user,jqfmt=vfsv0  1  2

#####################
quotacheck -augmn

quotacheck: 쿼터용 데이터베이스(즉, aquota.user, aquota.group) 생성

옵션 의미:

-a: /etc/mtab에 기록된 모든 파일시스템 점검
-m: 마운트 해제하지 않음
-n: 파일시스템을 실제 수정하지 않음 (단순 점검)

######################
quotaon -avug
quotaon: 쿼터 기능 활성화

-a: 모든 파일시스템
-v: 상세 출력

######################
quotaoff -avug
quotaoff: 쿼터 기능 비활성화

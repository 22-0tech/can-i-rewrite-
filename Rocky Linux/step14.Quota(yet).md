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


#######################

UUID="73e62b26-8ae6-4d04-921c-831c55c3faa9"  /home3  xfs  defaults,uquota,gquota  0  0
/home3 파티션에 XFS용 쿼터 기능을 활성화

uquota: 사용자 쿼터

gquota: 그룹 쿼터
→ usrjquota, jqfmt는 ext4용이라 XFS에서는 사용 안 함

📌 수정 후 반드시 재마운트

bash
코드 복사
mount -o remount /home3



xfs_quota -x /home3
-x: 관리자 모드(확장 명령 사용 가능)

/home3: 쿼터 적용할 파일시스템 경로



📊 3️⃣ 상태 확인
state


→ /home3 파일시스템에 사용자/그룹 쿼터가 활성화되어 있는지 확인
📈 4️⃣ 현황 보기
report -h


→ 현재 각 사용자/그룹의 디스크 사용량과 제한(soft/hard) 표시
(-h: human-readable, 단위 보기 좋게 표시)


🚫 5️⃣ 사용자별 제한 설정
limit bsoft=1G bhard=2G quota3


limit: 쿼터 설정 명령

bsoft: 소프트 제한 (1GB 넘으면 경고)

bhard: 하드 제한 (2GB 넘으면 저장 불가)

quota3: 사용자 이름

✅ 결과 →
quota3 사용자는 /home3 파티션에 최대 2GB까지만 파일 저장 가능


################################

SCSI 디스크 50G 1개를 /qhome1 마운트하시오.

2명의 유저에게 다음을 구성하시오.

xfs로 /qhome1에 마운트
4gluser1 블록 소프트 30M 하드 50M
4gluser2 블록 소프트 100M 하드 500M

이후 /etc/fstab에 등록 시 반드시 장치명이 아닌 해당 파티션의 UUID로 등록하시오.

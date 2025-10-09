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

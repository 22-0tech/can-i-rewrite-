디스크 관리 유연성을 극대화 


물리 디스크 → PV → VG → LV → 파일시스템 → 마운트

물리 디스크 준비 (Physical Volume, PV)

pvcreate /dev/sdb1 /dev/sdc1




볼륨 그룹 생성 (Volume Group, VG)

vgcreate 4glgrp1 /dev/sdb1 /dev/sdc1



논리 볼륨 생성 (Logical Volume, LV)

lvcreate -L 50G -n mylv1 4glgrp1
lvcreate -L 500M -n mylv2 4glgrp1
lvcrate -L 100%FREE -n mylv3 4glgrp1



(vgextend 4glgrp1 /dev/sde1
vgextend 4glgrp1 /dev/sdf1

vgreduce 4glgrp1 /dev/sde1

lvextend -l 400 /dev/4glgrp1/mylvm1
lvextend -L 500M /dev/4glgrp1/mylvm4)

-L = 절대 용량(MB, GB 등)

-l = VG 단위의 논리 단위(PE) 수





파일시스템 생성

xfs의 경우
xfs_growfs /mylvm4

ext4의 경우
resize2fs /dev/4glgrp1/mylvm1



마운트 및 사용

LVM 삭제

mount 해제
lvremove /dev/grp2/lv1
vgremove grp2
pvremove /dev/nvme0n1p1

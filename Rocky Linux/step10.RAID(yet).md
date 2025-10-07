RAID 레벨	     최소 디스크 수  	장점
Linear / JBOD   	1	            용량 합산, 단순
RAID 0	          2	            성능 향상, 용량 합산
RAID 1          	2	           데이터 보호(미러링)
RAID 5           	3	           데이터 보호(1개 디스크), 읽기 성능 ↑, 용량 효율 좋음
RAID 6            4	     데이터 보호(2개 디스크), 읽기 성능 ↑
RAID 10          	4	           데이터 보호 + 성능 향상 (미러링+스트라이핑)











파티션을 레벨 Linear로 합치는 명령어입니다.

mdadm--create /dev/md5 --level=Linear --raid-devices=2 /dev/sdb1 /dev/sdc1


mdadm--create /dev/md6 --level=6 --raid-devices=4 /dev/sdd1 /dev/sde1 /dev/sdf1 /dev/sdg1

mdadm --detail --scan > /etc/mdadm.conf


##사진

mkfs.xfs /dev/md5 
mount /dev/md5 /Raid linear
mkfs -t ext4 /dev/md6
mount /dev/md6 Raid 6

vi /etc/fstab

echo "/dev/md5 /raidLinear xfs defaults 0 0" >> /etc/fstab
echo "/dev/md6 /Raid 6 ext4 defaults 0 0" >> /etc/fstab








mdadm --detail /dev/md5
mdadm --detail /dev/md6

mdadm --detail --scan
전체 레이드 보기








메타데이터 - 레이드 구성 정보를 디스크에 담고 있는 구간





df -hT

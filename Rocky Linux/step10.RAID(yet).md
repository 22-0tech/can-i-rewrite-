RAID 레벨	     최소 디스크 수  	장점
Linear / JBOD   	1	            용량 합산, 단순
RAID 0	          2	            성능 향상, 용량 합산
RAID 1          	2	           데이터 보호(미러링)
RAID 5           	3	           데이터 보호(1개 디스크), 읽기 성능 ↑, 용량 효율 좋음
RAID 6            4	     데이터 보호(2개 디스크), 읽기 성능 ↑
RAID 10          	4	           데이터 보호 + 성능 향상 (미러링+스트라이핑)













mdadm--create /dev/md1 --level=? --raid-devices=? /dev/sd1 /dev/sd1












mdadm --detail /dev/md?

mdadm --detail --scan
전체 레이드 보기





메타데이터 - 레이드 구성 정보를 디스크에 담고 있는 구간





df -hT

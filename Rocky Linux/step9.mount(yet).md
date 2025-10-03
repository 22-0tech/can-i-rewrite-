**mount<br>
<br>
Mounting is connecting a computer so that it can read and write files on a USB drive or hard disk.<br>
*컴퓨터가 USB나 하드디스크 안에 있는 파일을 읽고 쓸 수 있도록 연결하는 것<Br>
<Br>
<Br>



*Four steps to mount<br>
과정 4단계<br>
<br>
<br>



1. Disk is checked 디스크 확인

![image break](../Pictur/step5/mount1.png)<br>
There are disks sdb and sdc.<br>
디스크 sdb, sdc가 있습니다.<br>
<br>




2. Partition is created 파티션 생성

![image break](../Pictur/step5/mount-2.png)<br>
For disk sdb, a partition is created first, and after creation, it must be saved using the write (w) command.<br>
먼저 sdb 파티션을 생성하는데, 생성 후 꼭 저장(w)을 해야합니다.
<br>
<br>



![image break](../Pictur/step5/mount3.png)<br>
For disk sdc, a partition is also created.<br>
디스크 sdc도 파티션 생성합니다.<br>
<br>



![image break](../Pictur/step5/mount-4.png)<br>
Partitions sdb1 and sdc1 have been created.<br>
sdb1, sdc1 파티션이 생성됐습니다.<br>
<br>
<br>


3. File system is created 파일시스템 생성


![image break](../Pictur/step5/mount5.png)<br>
A file system (format) must be created on the newly created partitions.<br>
생성된 파티션에 파일 시스템(포맷)을 생성해야 합니다.<br>

There are four types of file systems: ext2, ext3, ext4, and xfs.<br>
Modern Linux primarily uses ext4, while xfs is employed for large-capacity or specialized use cases.<br>
파일 시스템은 ext2, ext3, ext4, xfs 4종류가 있습니다.<br>
최신 리눅스는 etx4를 주로 이용하며 대용량 같은 용도에 따라서 xfs를 이용합니다.<br>

The commands are as follows: mkfs -t ext4 or mkfs.ext4 for ext4, and mkfs.xfs for xfs.<br>
명령어는 각각 mkfs -t ext4 = mkfs.ext4 / mkfs.xfs입니다.




![image break](../Pictur/step5/mount6.png)<br>
It is possible to verify that each file system has been applied correctly.<br>
각각 파일시스템에 맞게 적용된 걸 볼 수 있습니다.<br>
<br>
<Br>
<Br>



4. Mounting is performed 마지막 단계<br>

![image break](../Pictur/step5/mount7.png)<br>
Before mounting, a directory is created to serve as the mount point. The mount point is a directory.<br>
마운트 하기 전에 어디에 마운트 할 건지 디렉토리를 만듭니다. 마운트 포인트는 디렉토리입니다.<br>





ㅡ vi /etc/fstab

![image break](../Pictur/step5/mount-8.png)<br>
<br>
*completed<br>
완료

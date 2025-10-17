**RAID<br>
<br>
A technology that combines multiple disks into a single device to improve performance and protect data.<br>
디스크를 하나의 장치를 묶어 성능 향상 및 데이터를 보호하는 기술<br>
<Br>
<Br>

RAID-Level&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Minimum number of disks&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Advantages<br>

Linear   	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     Combined capacity<br>
RAID 0	 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2	     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Performance improvement<br>
RAID 1           &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2 	    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Data protection (mirroring)<br>
RAID 5        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3	      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  High capacity efficiency<br>
RAID 6           &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4	       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Data protection (2 disks)<br>
RAID 10          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4	       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Data protection + performance improvement (mirroring + striping)<br>

<br>
<Br>
<br>
<br>





First, the RAID level is Linear. The minimum number of disks is 1.<br>
*Why – however, for technical reasons, it is usually used with at least 2 disks.<br>

먼저 RAID 레벨 Linear입니다. 최소 디스크 수가 1개입니다.<br>
*Why-하지만, 기술적인 의미를 위해 보통 2개부터 사용합니다.<br>
<br>
<br>


![image break](../Pictur/step10/raid1.png)<br>
First, create the partition.<br>
먼저 파티션을 생성합니다.<br>
<br>
<br>
<Br>

![image break](../Pictur/step10/raid2.png)<br>
This is the command to create a RAID device.<br>
Fill in the items according to the RAID requirements, and md(x)—where x is arbitrarily set by the user.<br>
RAID 장치 생성 명령어입니다. RAID 조건에 맞게 항목을 써주고 md(x) x는 사용자 임의 설정입니다. <br>

<br>
The RAID level is 6. The same process can be followed.<br>
레벨 6입니다. 같은 과정으로 할 수 있습니다.<br>

![image break](../Pictur/step10/raid3.png)<br>

<br>
<Br>

Command : lsblk

![image break](../Pictur/step10/raid4.png)<br>
The RAID status can be checked.<br>
RAID 잘 된 걸 볼 수 있습니다.<br>



<br>
<Br>
<Br>
<br>
This is a summary of all RAID devices.<br>
RAID 전체 장치 요약입니다.<br>
<br>

![image break](../Pictur/step10/raid5.png)<br>
If sent to /etc/mdadm.conf, it is saved on the disk and activated at boot.<br>
/etc/mdadm.conf로 보내면 디스크에 저장되어, 부팅시에 활성화 됩니다. <BR>
<br>
<br>
<Br>


![image break](../Pictur/step10/raid6.png)<br>
Additionally, the RAID status can be viewed in real time using this command.<br>
또한, 해당 명령어를 이용해 실시간 RAID 상태를 볼 수 있습니다.<br>
<br>
<br>
<br>
<Br>
<br>


![image break](../Pictur/step10/raid7.png)<br>


![image break](../Pictur/step10/raid8.png)<br>



![image break](../Pictur/step10/raid9.png)<br>
Proceed with the mounting steps (step 9): format the disk, create the mount point, and mount it.<br>
마운트하는 과정대로(step9) 포맷과 마운트 포인트 생성 후 마운트합니다.<br>
<br>
<Br>


vi /etc/fstab

![image break](../Pictur/step10/raid10.png)<br>
If the mount point and format type are saved correctly, <br>
the configuration itself is stored on the disk, and the RAID device is automatically mounted at boot.<br>
형식에 맞게 마운트 포인트 및 포맷 형식을 설정하면,<br>
설정 자체가 디스크에 저장되어 부팅시, 자동으로 RAID장치를 마운트합니다.<br>
<br>
<Br>
The commands : df -hT and blkid can be used.<br>
df -hT 및 blkid를 활용할 수 있습니다.<br>
<br>
<Br>
<Br>
<Br>
<Br>
<Br>




* Reset<br>
* 초기화<br>
<br>
Reset can be performed by reversing the steps of the RAID mounting process.<br>
초기화는 RAID 마운트하는 과정 반대로 진행하면 됩니다.<br>
<br>
<Br>
<Br>
<Br>


![image break](../Pictur/step10/raid11.png)<br>
Each mount is unmounted.<br>
각각 마운트 해제를 합니다.<br>
<Br>
<Br>
<Br>




![image break](../Pictur/step10/raid12.png)<br>
Next, the RAID array is stopped so that it is no longer in use.<br>
Once stopped, it appears as a regular partition.<br>
<Br>
<Br>
<Br>



그 다음은, RAID 배열을 더 이상 사용하지 않도록 중지시키는 것입니다.<br>
중지시키면, 일반 파티션처럼 보이게 됩니다.<br>

![image break](../Pictur/step10/raid13.png)<br>
By erasing the RAID information (metadata) stored on the disk,<br>
any trace of the disk having been part of a RAID is removed.<br>
디스크에 저장된 RAID정보 (메타데이터)를 지움으로써,<br> 
디스크가 RAID의 일부였다는 흔적이 사라지게 됩니다.<br>
<br>
<br>
<Br>


![image break](../Pictur/step10/raid14.png)<br>
The disks are left with only partitions, just like before the RAID was created.<br>
RAID생성 전처럼 파티션만 남은 상태가 됩니다.<br>



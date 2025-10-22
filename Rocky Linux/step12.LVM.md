**LVM<br>

A system that manages disk space flexibly.<br>
디스크 공간을 유연하게 관리하는 시스템<br>
<br>
<br>

* Process<br>
* 과정<br>
<br>


Physical disk → PV → VG → LV → (Filesystem → Mount)<br>

물리 디스크 → PV → VG → LV → (파일시스템 → 마운트) <br>
<br>
<br>
<br>

lsblk

![image break](../Pictur/step12/lvm1.png)<br>


<br>
<Br>

![image break](../Pictur/step12/lvm2.png)<br>
pvcreate is the step that prepares a disk for use as an LVM physical volume (PV).<br>
pvcreate 디스크를 LVM으로 준비하는 단계<br>
<br>
<br>

![image break](../Pictur/step12/lvm3.png)<br>
(Volume Group, VG)<br>

vgcreate vg_data /dev/sdb<br>
<Br>
<Br>




![image break](../Pictur/step12/lvm4.png)<br>
Create a Logical Volume (LV) in vg_data with absolute size -L 17GB and name -n lv_backup<br>
논리 볼륨 생성 (Logical Volume, LV)<br>
절대용량 -L 17GB, 이름 -n lv_backup을 vg_data에 생성 
<br>
<br>


![image break](../Pictur/step12/lvm5.png)<br>
It is possible to check/verify the LVM configuration.<br>
lvm을 확인할 수 있습니다.


<br>
<br>
<br>

* Lvm Remove<Br>
<Br>

It can be performed in the reverse order of the creation process.<Br>
과정의 반대로 진행하면 됩니다.<br>
<br>
<Br>

![image break](../Pictur/step12/lvm6.png)<br>
LV Remove<br>
<br>

![image break](../Pictur/step12/lvm7.png)<br>
VG Remove <br>
<br>

![image break](../Pictur/step12/lvm8.png)<br>
PV Remove<br>
<br>

![image break](../Pictur/step12/lvm9.png)<br>
Deletion completed.<br>
삭제 완료<br>










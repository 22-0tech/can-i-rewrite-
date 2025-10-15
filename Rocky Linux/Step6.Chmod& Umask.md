**Chmod <br>
<br>

File access permission change command<br>
파일 접근 권한 변경 명령어<br>
<br>
<br>

Linux files have read (r), write (w), and execute (x) permissions.<br>
File permissions can be represented in two ways.<br>

ㅡ 리눅스 파일에는 읽기(r),쓰기(w),실행(x) 접근 권한이 있는데<br>
접근 권한을 2가지로 표현할 수 있습니다.<br>
<br>

<br>
Using letters & symbols<br>
* 문자 & 기호를 이용한 방법<br>
<br>

![image break](../Pictur/step6/chmod-1.png)<br>

Read permission (r) for all users (all)<br>
모든 사용자(all)에게 읽을 권한(r)<br>

![image break](../Pictur/step6/chmod-2.png)<br>

<br>

⬇ ⇩


![image break](../Pictur/step6/chmod-3.png)<br>


<br>
<br>

Execute permission (x) for the file owner (u) only<br>
파일 소유자(u)에게만 실행(x) 권한<br>

![image break](../Pictur/step6/chmod-4.png)<br>

![image break](../Pictur/step6/chmod-5.png)<br>

Using octal numbers: 4 (r), 2 (w), 1 (x)<br>
* 8진수 숫자를 이용한 방법 4(r),2(w),1(x) <br>

![image break](../Pictur/step6/chmod-6.png)<br>
<br>
<br>


**Umask<br>

The value displayed by changing the default permissions<br>
기본 접근 권한을 변경하여 출력하는 값<br>

The default umask is 022<br>
umask는 기본적으로 022<br>

![image break](../Pictur/step6/umask1.png)<br>
For the why-Security file, the default permissions are 666.<br>
666 − 022 = 644, so the file is created with this permission when it is first created.<br>
why-Security 파일의 경우 기본 권한이 666으로 되어있습니다.<br>
666-022=644 이 값으로 파일이 처음 생성될 때 만들어집니다. <br>

![image break](../Pictur/step6/umask2.png)<br>



For directories, the default permission is 777. It is created after subtracting the umask value.<br>
디렉터리의 경우 기본 권한이 777입니다. umask값만큼 빠진 후 생성됩니다.<br>
<br>
<br>

**special permissions<br>
특수권한<br>


4  SetUID<br>
![image break](../Pictur/step6/umask5.png)<br>
The file is executed with the owner’s permissions.<br>
파일을 실행할 때 소유자 권한으로 실행합니다.<br>
<br>
<br>
<br>


2  SetGID<br>
![image break](../Pictur/step6/umask4.png)<br>
The file is executed with the group’s permissions.<br>
파일을 실행할 때 그룹 권한으로 실행합니다.<br>
<br>
<br>
<br>


1 Sticky bit<br>
![image break](../Pictur/step6/umask3.png)<br>
Other users cannot delete files in the directory.<br>
디렉터리에서 다른 사용자가 파일을 삭제 못합니다.<br> 

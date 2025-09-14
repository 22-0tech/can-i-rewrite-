** Router Security <br>
<br>



![image break](../../Pictur/step4/passwd-1.png) <br>

Set the password to AAA to enter privileged mode from user mode.<br>
사용자 모드에서 관리자 모드로에 진입비밀번호를 AAA로 설정합니다. 

![image break](../../Pictur/step4/passwd-2.png) <br>
The password is in uppercase letters.<br>
비밀번호는 대문자입니다. 
<br>

![image break](../../Pictur/step4/passwd-3.png) <br>
When accessing the device physically or via Telnet, the password can be exposed in plain text.<br>
장비에 물리적 접근 또는 Telnet 접속 환경에서는 비밀번호가 그대로 노출될 수 있다.


![image break](../../Pictur/step4/passwd-4.png) <br>
Cisco Type 7 – Weak Encryption<br>
Cisco Type 7 약한 암호화 

![image break](../../Pictur/step4/passwd-5.png) <br>
MD5 Hash – Stronger Encryption<br>
MD5해시값 강한 암호화 

![image break](../../Pictur/step4/passwd-6.png) <br>
<br>
<br>
<br>
<br>
![image break](../../Pictur/step4/passwd-7.png) <br>

![image break](../../Pictur/step4/passwd-8.png) <br>
Even if no service password-encryption is configured, the passwords remain encrypted.<br>
no service password-encryption해도 그대로 암호화 되어있음 


![image break](../../Pictur/step4/passwd-9.png) <br>
Removing the enable password using no enable password.<br>
no enable password 비밀번호 해제 

![image break](../../Pictur/step4/passwd-10.png) <br>

![image break](../../Pictur/step4/passwd-11.png) <br>
sh run = show running-config


![image break](../../Pictur/step4/passwd-12.png) <br>
line vty 0 4 VTY 원격 접속용 가상 포트 0~4번 라인
password b VTY 접속 시 비밀번호를 b로 설정 
login 패스워드 인증 활성화
transport input telnet VTY 라인에서 Telnet 접속만 허용
transport input all 모든 원격 접속 프로토콜 허용 (SSH만 허용하는 것이 안전)
![image break](../../Pictur/step4/passwd-13.png) <br>

PC로 라우터에 텔넷 접속 비밀번호 b 입력 그러나 라우터에 비밀번호가 없으므로 관리자 모드에 진입 불가 









**ssh-keygen

공개키는 rsa기반을 만들어져 안전 비밀번호보다 안전하며 편리합니다.


id_rsa, id_rsa.pub 파일 확인



공개키 전달 후 로그인 



SSH 접근 제어
vi /etc/ssh/sshd_config

40행의 PermitRootLogin no
root 로그인 허용 여부

65행의 PasswordAuthentication no
패스워드 사용 가능 여부
vi 저장 후 나가기
Esc
:wq = :x
systemctl restart sshd
firewall-cmd --add-port=50001/tcp


Rocky 9 SSHD 설정 파일 변화
/etc/ssh/sshd_config.d
설정을 일부분 떼어서 추가적으로 보관

root로 원하는 유저에게 sudo 권한 부여
visudo
111행
4gl   ALL=(ALL)   NOPASSWD: ALL
(vi에서 행 번호를 출력
:set number
:set nu
)

71행 PasswordAuthentication no


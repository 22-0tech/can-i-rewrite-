** NAT<br>
<br>
<br>

- Static<br>



(Packet Tracer)
![image break](../../Pictur/step9/NAT.2t.png) <br>
first, set the IP address to be used for translation when traffic goes from internal to external.<br>
And then, configure the router’s external and internal interfaces accordingly.<br>
먼저, 내부에서 외부로 나갈 때 변환 될 IP를 설정 후, 라우터 기준 외부 및 내부 인터페이스 설정 



![image break](../../Pictur/step9/NAT.3.png) <br>
<br>
To undo it, use no ip nat inside source static.<br>
지울 때는 no ip nat insde source static [IP주소]



<br>
<br>
<br>
<br>
<br>


- Dynamic<br>
<br>



(Packet Tracer)

![image break](../../Pictur/step9/NAT.4.png) <br>
First, create a NAT pool (name it 'B') <br>
Next, create an ACL (Access Control List) <br>
Finally, apply dynamic NAT using the pool.<br>

ㅡ NAT 풀 생성 (이름 B)<br>
ㅡ ACL 생성<br>
ㅡ 동적 NAT 풀 적용<br>
<br>
<br>
<br>
<br>



- PAT<br>

When no pool is used, each internal IP is distinguished by its external port number.<br>
*pool 없이 외부포트 번호로 (포트 번호 다르면 내부 IP 다름)

(GNS3)

![image break](../../Pictur/step8/NAT.1.png) <br>







![image break](../../Pictur/step9/NAT.5.png) <br>











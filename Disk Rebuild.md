### 디스크 Rebuild
- Internet URL에 Server의 IP를 입력하여 ILO에 접속하였고, System Information -> Storage에 들어가서 Disk가 정상작동한 것을 확인한 뒤, SAS디스크 하나를 빼서 Disk Trouble을 만들었다.

- Disk Rebuild 방법(BIOS) : SAS Disk를 다시 Server에 삽입한 후 (BIOS) System Configuration -> Main Menu -> Drive Management에 들어가면 Disk가 Rebuild하는 것을 확인할 수 있다. 

- Disk Rebuild 구성 상태 확인(ILO) : (ILO) System Information -> Storage에 접속하면 확인 가능하다. 

### Raid 설정 / 디스크 구성 
- Server(SATA Disk 2개와 SAS Disk 3개를 삽입) BIOS에서 연결되어 있는 디스크 확인, Raid 구성(SAS디스크만 사용 Raid 5로 구성)을 한 뒤 ILO 연결 전 아이디와 비밀번호를 만들었고, IP를 확인 이후 OS(SAS Disk / Raid5)를 설치하였다.

## HP DL360 Gen8 Server Red Hat Linux 설치 
### 1. 준비 사항 
- Red Hat Linux 설치 이미 (ISO 파일) : Red Hat 고객 포털에서 다운 받을 수 있다. ( rhel-9.5-x86_64-boot 사용 )
- 부팅 가능한 USB 드라이브 또는 DVD : 설치 이미지를 담을 수 있는 용량의 저장 매체 필요 (CD드라이브로 구워서 사용)
- Server의 네트워크 연결 : Server에 LAN선을 연결하여 네트워크를 통해 업데이트 및 추가 소프트웨어 설치 가능 

### 2. 설치 미디어 생성 
- Red Hat Linux ISO 이미지를 CD 에 굽는다. 

### 3. 서버 BIOS 설정 
- F9 : System BIOS 세팅 초기화 가능 
- F5 : Smart Array Controller에서 Raid 구성
- F11 -> One Time Boot Menu : Mount할 저장장치 확인 

※ BIOS 화면에서 가만히 있어도 Red Hat Linux 설정으로 들어가진다. 

### 4. Red Hat Linux 설치 
- 빨간색으로 표시된 Root, 소프트웨어 설정, Disk설정 등 기입 후 Server Reboot 하면 설치가 완료 된다. 

※ Reboot 하고 BIOS화면에서 가만히 있으면 된다. 
<br>

### ※ Gen9, 10, 10 plus 등 Linux 설치구성은 비슷하지만, GUI가 많이 다르다.
 

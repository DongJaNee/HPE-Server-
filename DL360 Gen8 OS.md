## HP DL360 Gen8 Server Window OS (USB) 설치 
### 1. 준비 사항 
- Red Hat Linux 설치 이미 (ISO 파일) : Red Hat 고객 포털에서 다운 받을 수 있다. ( rhel-9.5-x86_64-boot 사용 )
- Microsoft에서 다운받을 Window OS를 설치 (설치과정에서 ISO 파일 / USB에 저장하는 것을 선택할 수 있다.) 
- 부팅 가능한 USB 드라이브 또는 DVD : 설치 이미지를 담을 수 있는 용량의 저장 매체 필요 (USB연결)
- Server의 네트워크 연결 : Server에 LAN선을 연결하여 네트워크를 통해 업데이트 및 추가 소프트웨어 설치 가능 

### 2. 설치 미디어 생성 
- Window OS 설치 후 USB로 옮긴다. 

### 3. 서버 BIOS 설정 
- F9 : System BIOS 세팅 초기화 가능 
- F5 : Smart Array Controller에서 Raid 구성
- F11 -> One Time Boot Menu : Mount할 저장장치 확인 (USB는 3번)

※ BIOS 화면에서 가만히 있어도 Window OS 설치과정으로 들어가진다. 

### 4. Window OS 설치 
- OS 설치화면에서 기존 Gen9 이상 모델과 같이 설치를 하고
- 설치가 완료되면 Server에 연결된 USB를 해제하고 Reboot시킨다.

※ Reboot 하고 BIOS화면에서 가만히 있으면 된다. 

 

## DL380 Gen10 Plus OS 설치 방법

![image](https://github.com/user-attachments/assets/678625d2-ac3f-48e2-8d55-9a15e549e130)
![image](https://github.com/user-attachments/assets/e497310a-b4fa-4647-8449-605f75d74ddc)

---

### **1. Windows 설치 후 드라이버 올리는 방법**
- **One-Time Boot Menu** -> **Rear USB 1: IODD iodd2531** -> 한번 부팅 -> BIOS 실행화면에서 ESC를 눌러 저장
- Windows 설치 후 Windows 화면에서 장치 관리자 접속 -> 네트워크 어댑터 확인하여 '!'가 뜨는지 확인
- (IODD에서) **ISO** -> **HP SW** -> **SPP** -> **SPP Gen 10 Plus** -> **Launch sum** -> 그러면 AHS가 다운받아진다. 이후 자동으로 웹사이트가 나오는데 그 웹사이트에서 설정  
  (Localhost Guided Update(Server와 IODD랑 버전을 비교해서 최신으로 업데이트하는 곳)) -> **Interactive(수동)** / **Automatic(자동)** 선택  
  ※ HPE Gen 10 Plus SPP download를 검색해서 로그인하면 필요한 Software를 다운받을 수 있다.  
  **(HPE 파트너 이상부터 다운로드 가능)**

---

### **2. BIOS Intelligent Provisioning(IP)을 사용해서 Driver를 올리는 방법 (Windows 설치 전)**
- BIOS 실행화면에서 **F10**을 누른 후 -> **Intelligent Provisioning** -> **Performance Maintenance**  
  **※ BIOS에서도 설치가 가능하지만, 시간이 많이 소요되므로 잘 사용하지 않는다.**

---

### ILO의 라이센스 넣는 방법 (장비마다 라이센서를 구매해야 함)
- **ALO Administration** -> **Licensing** 접속 -> **license의 Key 값**을 넣으면 된다.

---

### HPE 380 Gen10 Plus ILO

![image](https://github.com/user-attachments/assets/0621b59d-0e3a-4f6f-b0e6-ecbdf268d4f3)

- **2U**는 **1U**보다 부품이 많고 크기가 커서 로딩 시간이 길고 소리가 더 크다.
- **IRO의 아이디 비밀번호**는 서버 장비 전원 밑 카드의 **User Name**과 **Password**를 참고하면 된다.
- **Lifecycle Management** 하에 노트북으로 BIOS 화면 확인 가능.
- HPE 서버 부팅 중 확인할 수 있는 정보: **메모리**, **사용 가능한 메모리**, **코어의 개수**, **시리얼 넘버** 등이 있다.

---

### ILO Information

![image](https://github.com/user-attachments/assets/d4a36aaa-e53e-4915-aee0-5b8cc8944a3f)

- **디스크 장애 처리 시** Part Number 확인 (디스크 고유 번호를 확인하여 정확한 장애 처리가 가능하다.)
- **Link Up**: 연결 완료
- **Link Down**: 연결 해제
- 시스템 정보는 **ILO System Information**에서 확인하는 것이 정확하다.
- **Device Inventory**: 주변 장치 구성 확인
- **ILO Storage**: 디스크 구성 상태 확인 가능
- **Administration**: ILO 아이디 비밀번호 생성 / 삭제 가능

---

### System Configuration
- **Slot**: 서버 메인보드나 다른 컴포넌트에 추가 장치나 카드를 삽입할 수 있는 물리적인 공간
- **Port**: 서버나 다른 장치에 연결되는 물리적인 인터페이스, Slot에 여러 Port가 장착된다.
- **Storage Slot**: 레이드 컨트롤 가능 (**Configuration Management에서 Create Logical Drive 선택**)
- **System Utilities** -> **System Information**: 시스템 정보 확인
- **BIOS에서의 HPE와 DELL의 차이점**: HPE가 더 상세하게 설명되어 있다.

---

### 케이블
- **UTP(Category)**: 1Gbps
- **지비기 광통신(광케이블)**: 10Gbps ↑

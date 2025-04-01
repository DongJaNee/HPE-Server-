## HBA란?
- **Host Bus Adapter**의 줄임말
- **서버와 다른 장비 사이의 통신을 위해 서버에 장착하는 카드**이다.
- 모든 장비가 같은 인터페이스를 갖추고 있지 않기 때문에 호환을 위해 필요하다.

#### 종류
- **Fibre Channel HBA**, **SCSI HBA** 등

![image](https://github.com/user-attachments/assets/0677c908-75f1-44a4-8fe4-039274d999f8)

#### SFP 포트
![image](https://github.com/user-attachments/assets/5aed03af-a105-4671-b556-f4a0b170bbd8)

---

### FC HBA란?
- **Fibre Channel HBA**의 줄임말
- **FC를 사용할 수 있도록 호스트에 설치되는 PCI 카드**이다.
- FC HBA 기반의 **DAS** 혹은 **SAN**과 연결하여 호스트와 **Disk Array**간에 인터페이스를 할 수 있도록 하는 HBA.

  **※ NIC만 장착된 장비에서 FC 케이블 사용하려면 별도 HBA를 장착해야 한다.**

#### FC HBA PCI 카드가 서버에 설치되어 있다면
- **Server** - **FC cable** - **Storage**

![image](https://github.com/user-attachments/assets/d1806806-63e4-4137-8a71-6d83482663a5)


---

### 스토리지 관리자 접속
1) 스토리지의 **IP 주소**를 URL에 입력하여 접속하면 스토리지의 **관리자 홈페이지**에 접속하여 **Storage에 연결된 Disk**를 확인하고 **Raid 구성**을 할 수 있다.
2) **FC 케이블**을 서버와 스토리지에 연결하고, 스토리지의 디스크 메모리를 할당하여 서버에 설치한다.
3) 서버에서 **하드 디스크 파티션 만들기** 및 **포맷**을 검색하고, 스토리지에서 받은 디스크를 **온라인**으로 바꾼 뒤 디스크를 사용할 수 있게 정상 상태로 바꾸어주면 **내PC에 디스크**가 추가된 것을 확인할 수 있다.

**※ Storage Model**  
- **P2000 G3**, **MSA2040**, **MSA2050**의 ID 기본값: **manage**  
- **PW 기본값**: **!manage**
- **Storage 기본 IP값**: (A: 10.0.0.2), (B: 10.0.0.3)

**Windows Server HBA WWN 포트 연결 확인**  
- CMD -> powershell 실행 -> `get-initiatorport` 실행하여 확인  
(Storage와 Server의 몇 번 Port에 연결되어있는지 확인 가능)

---

### Linux 서버 운영체제 지원
- **HPE**: **HPE OS Support matrix**를 Google에 검색하여 필요한 것을 찾아서 쓰면 된다.
- **DELL**: **DELL OS Support matrix**를 Google에 검색하여 필요한 것을 찾아서 쓰면 된다. (HPE보다 복잡함)

---

### Linux 소개
- **Red Hat**, **Centos**, **Ubuntu**, **Oracle**, **Rocky** 등 (Linux는 명령어가 대부분 비슷하다)  
- **Vmware** - Windows와 Linux 둘 다 설치 가능  
- **Red Hat** (유료), **Centos** (무료)

---

### NIC
- **TX / UTP** -> 1G / 10G
- **SX / LC / 광** -> 1G / 10G / 25G (지비기랑 규격이 같다) / 40G / 56G / 100G
- **FC HBA 케이블**: 4G / 8G / 16G / 32G / 64G

---

### 광케이블
- **광섬유**는 유리 또는 플라스틱 섬유를 따라 빛으로 정보를 전송하는 기술
- **광케이블**은 장거리 및 고성능 데이터 네트워킹에 많이 사용한다.
- **SAN 환경**에서 서버와 **SAN 스위치** 또는 **스토리지**와 **SAN 스위치**를 고속으로 연결하기 위해 사용한다.

1) **OM2** 네트워크 1G까지만 지원 / **FC HBA** 4G까지만 지원  
2) **OM3** 네트워크 1G / 10G / 25G / **FC HBA** 4G / 8G / 16G / 32G  
3) **OM4** 네트워크 1G / 10G / 25G / **FC HBA** 4G / 8G / 16G / 32G (OM3보다 전송거리가 더 길다)

---

### AMD와 Intel 서버 모델 구분
- **AMD**: HPE Server 뒤에 숫자 **5**가 붙는다. (예: **DL 385**)
- **Intel**: HPE Server 뒤에 숫자 **0**이 붙는다. (예: **DL 380**)

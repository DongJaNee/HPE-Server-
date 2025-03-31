## HPE 디스크 Clear 및 재구성
- BIOS 화면에서 **System Configuration**을 접속 -> 맨 밑 **Storage** 클릭 -> **Main Menu** 접속하면 **Disk Clear** 및 **Raid 구성**, **상태 확인** 등을 할 수 있다.

  **※ SATA Disk와 SAS 디스크는 호환되지 않지만, Server에 SATA와 SAS Disk 둘 다 삽입하면, 각각 따로 Raid 설정을 할 수 있고, 필요에 따른 Disk 사용이 가능하다.**

---

## HPE OS설치
- **IODD**를 Server에 연결한 뒤 **Windows2022**에 접속하여 설치한다.

---

## Drive 설치
- Disk 설정과 OS를 설치하였으면, **Window 내 PC Drive** 접속하여 **Launch Sum**을 클릭하면 **cmd**가 업데이트된다.
- 업데이트가 끝나면 자동으로 **Localhost Guided Update**가 자동으로 켜지는데, HPE에서 호환을 선호하는 것을 업데이트하려면 **Auto**로 설정하여 업데이트를 진행해야 한다.
- 업데이트가 끝나면 **장치 관리자**에 접속 -> 장치들에 '**!**'가 사라진 것을 확인하면 끝이다.

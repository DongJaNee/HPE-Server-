# ProLiant DL380 Gen10 BIOS 연결 조작 및 확인

## 1. System Configuration

![image](https://github.com/user-attachments/assets/f942e591-61b0-4676-b425-08f756bce0b9)

---

![image](https://github.com/user-attachments/assets/f3a2b5be-0e8c-423f-9a75-0ab30cf6c7c9)

- **서버명**: ProLiant DL380 Gen10  
  - (*System Configuration* -> System Information -> Summary에서 확인 가능)
- **디스크**: Box: 3, Bay: 1, Size: 480.1GB SATA-SSD ATA SAMSUNG MZ7L3480  
  - (*System Configuration* -> HPE Smart Array P408i-a SR Gen10 -> Array Configuration -> Create Array에서 디스크 확인 가능) 
---

![image](https://github.com/user-attachments/assets/5a7e28e1-1daa-4f50-97a8-b3a477673e73)

- **NIC**: 1 Gb-4-Part 331i 4port  
  - (*System Configuration*에서 확인 가능)  
  **※ NIC의 Number는 4-Port의 위치와 기존 설치 여부에 따라 달라질 수 있음**
- **HBA**: 16GB 2P FC 2Slot  
  - (*System Configuration*에서 확인 가능)
---

- **RAID 만들기**:  
 ->  ->  -> 디스크 체크 ->  -> RAID level 설정 -> 
1. System Configuration
   
  ![image](https://github.com/user-attachments/assets/b227c8b3-12f0-4475-aeec-4c471e68f636)

---
2. Disk Select
   
    ![image](https://github.com/user-attachments/assets/2253d29d-20a2-4393-a34d-31c4554895cf)

---
3. Array Configuration
   
    ![image](https://github.com/user-attachments/assets/c96e357c-7ca3-431b-a95e-5d129132cee8)
  
---
4. Create Array Disk Check
   
    ![image](https://github.com/user-attachments/assets/b69e86fc-7267-450f-a1bd-85455715cd46)

---
5. RAID Level Setting
   
    ![image](https://github.com/user-attachments/assets/d5f1b253-a941-406c-913c-b88b53ee3aa3)

---
6. Submit Change
   
    ![image](https://github.com/user-attachments/assets/65310376-8e36-4cdb-9943-4cb24c032992)

---
7. Back to Main Menu
    
    ![image](https://github.com/user-attachments/assets/8b6aca4c-032f-4b3f-a178-1aedcb7a855a)

---

- **RAID 선택 삭제**:  
  - *System Configuration* -> Raid -> Array Configuration -> Manage Array -> 삭제할 RAID 클릭 -> Delete
- **RAID 전체 삭제**:  
  - *System Configuration* -> Raid -> Configure Controller Setting -> Clear Configuration -> Delete All Array Configuration

---

## 2. System Information

![image](https://github.com/user-attachments/assets/d604b5d2-aecd-4aa8-8125-eb9e946b2962)

- **CPU**: Intel(R) Xeon(R) Gold 5222  CPU 
  - (*System Information* -> Processor Information에서 CPU 확인 가능)

--- 

![image](https://github.com/user-attachments/assets/9a8a64c4-c6d0-444b-bc33-2599ab9fdc67)

- **메모리**: DIMM 32GB  
  - (*System Information* -> Summary에서 메모리 용량 및 총량 확인 가능)

--- 
- **Power**: 800W x 2  
  - (서버 앞면에서 확인 가능)

---

## 3. OS 설치 방법

1. **remove film(IODD) 연결** -> Windows Server 2022 접속  
   - (*Windows를 Server에 Mount 시키기 위함*)
2. **One Time Boot Menu**:
   - Internal USB 1 : IODD iodd2531 선택  
   - 엔터 2번 -> 다음 -> 지금 설치 -> 사용자 지정 -> 드라이브 로드 -> 확인


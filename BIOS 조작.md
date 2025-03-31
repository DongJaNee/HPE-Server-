# ProLiant DL380 Gen10 BIOS 연결 조작 및 확인

## 1. System Configuration

- **서버명**: ProLiant DL380 Gen10  
  - (*System Configuration* -> System Information -> Summary에서 확인 가능)
- **디스크**: Box: 3, Bay: 1, Size: 480.1GB SATA-SSD ATA SAMSUNG MZ7L3480  
  - (*System Configuration* -> HPE Smart Array P408i-a SR Gen10 -> Array Configuration -> Create Array에서 디스크 확인 가능)
- **NIC**: 1 Gb-4-Part 331i 4port  
  - (*System Configuration*에서 확인 가능)  
  **※ NIC의 Number는 4-Port의 위치와 기존 설치 여부에 따라 달라질 수 있음**
- **HBA**: 16GB 2P FC 2Slot  
  - (*System Configuration*에서 확인 가능)
- **RAID 만들기**:  
  - *System Configuration* -> Raid -> Array Configuration -> Create Array -> 디스크 체크 -> Proceed to next form 클릭 -> RAID level 설정 -> Submit Change
- **RAID 선택 삭제**:  
  - *System Configuration* -> Raid -> Array Configuration -> Manage Array -> 삭제할 RAID 클릭 -> Delete
- **RAID 전체 삭제**:  
  - *System Configuration* -> Raid -> Configure Controller Setting -> Clear Configuration -> Delete All Array Configuration

---

## 2. System Information

- **CPU**: Silver 4214R  
  - (*System Information* -> Processor Information에서 CPU 확인 가능)
- **메모리**: DIMM 256GB  
  - (*System Information* -> Summary에서 메모리 용량 및 총량 확인 가능)
- **Power**: 800W x 2  
  - (서버 앞면에서 확인 가능)

---

## 3. OS 설치 방법

1. **remove film(IODD) 연결** -> Windows Server 2022 접속  
   - (*Windows를 Server에 Mount 시키기 위함*)
2. **One Time Boot Menu**:
   - Internal USB 1 : IODD iodd2531 선택  
   - 엔터 2번 -> 다음 -> 지금 설치 -> 사용자 지정 -> 드라이브 로드 -> 확인


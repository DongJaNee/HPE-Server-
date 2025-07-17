# AI and Energy
- AI workload를 사용할 때 전력 소모량이 많이 발생한다.
- 전력난에 대비하기 위해 DataCenter 옆 소규모 발전소를 두고있다.
- HPE의 냉각 방향성 : 보냉식 -> 수냉식
  **이점**
  1) 1.8% more performance with DLC
  2) 19.2% more performance with K/W DLC
  3) 70% Server gead goes to water(DLC)
  4) 30% server geat goes to air (fans) 

# Liquid Cooling : A Necessity for AI
| 항목              |  **Air Cooling **    |  **Liquid Cooling **      |
| --------------- | ---------------------------- | -------------------------------- |
| **열 밀도**        | 20\~30kW/rack              | 100\~150kW/rack 이상               |
| **장점**          | - 구축 비용 낮음<br>- 기존 시설과 호환 쉬움 | - 고성능 GPU에 최적<br>- 전력 및 공간 효율 우수 |
| **단점**          | - 냉각 한계<br>- 팬 소음과 높은 PUE    | - 초기 설치비용 높음<br>- 운영 복잡도 증가      |
| **AI 워크로드 적합성** | 중소 규모 AI<br>(일반 서버/ML 실험용)   | 초대형 AI<br>(LLM 학습, HPC, GB200 등) |

---
# AI 도입 시도가 어려운 이유 
- 기존 legacy solutions 환경이 존재하기 때문
- 운영이나 관리가 어렵다
- AI 모델 구축/운영에 필요한 인프라 부족하다 (GPU, 스토리지, 네트워크)

# AI Storage 도입시 중요한 점  
- Workload : 어떤 종류의 AI 워크로드를 처리할 것인가
- Workflow : 워크플로우 목표 시간 내 완료 가능 여부
- Capacity : 대규모 데이터를 저장할 수 있는가
- Infrastructure challenges : 냉각, 전력, 물리적 공간 등 인프라 제약 대응 가능한가

# AI training workflows 
| 단계                           | 주요 문제                                       | 요구 사항                                                  |
| ---------------------------- | ------------------------------------------- | ------------------------------------------------------ |
| **Data Loading**             | - GPU 기아 현상 (GPU가 데이터 기다리며 idle 상태)         |  낮은 지연 시간 (Low Latency)<br> 높은 처리량 (High Throughput) |
| **Checkpoint**      | - 읽기:쓰기 비율 2:1<br>- I/O 병목 발생 가능            |  전체 학습 시간의 **5% 이하 소요**<br> 빠른 쓰기 성능                 |
| **Gradient Synchronization** | - 다수의 GPU/노드 간 **모델 파라미터 동기화**<br>- 네트워크 병목 |  **고대역폭 네트워크**<br> 빠른 IOPS 지원                        |
| **Checkpoint**    | - 중간 실패 발생 시 복구 불가 위험                       |  **신뢰성 높은 스토리지**<br> 복구 가능한 백업 구조 (RAID, 중복 저장 등)    |

---

## GPU Focus 
- Performance
- Memory 

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

# AI Training 매커니즘 (Forward/Backward Propagation (순/역 전파))
- 순전파 -> 손실 계산 -> 역전파 -> 파라미터 업데이트
1. 학습 데이터셋 입력 및 순전파
 1) 모델의 첫 번째 입력 레이어 각 토큰은 숫자로 인코딩되어 벡터 형태로 전환
 2) 히든 레이어 통과 (선형 변환 + 활성화 함수) Weights와 Bkas을 곱하고 더하는 선형 변환 -> 활성화 함수

2. 손실 함수를 통한 Less Score 계산
 1) 최종 예측값과 실제 정답(참값)을 비교

3. 역전파 및 옵티마이저 적용 
 1) loss Score 기반 역추적 -> 경사 계산 -> 옵티마이저 파라미터 업데이트 

# GPU Memory 점유 구성 (Pre/Post Training GPU vs Inference GPU)

| 항목             |  **Pre/Post Training GPU**                                                        |  **Inference GPU**                     |
| -------------- | ----------------------------------------------------------------------------------- | ---------------------------------------- |
| **사용 목적**      | 모델 학습 (훈련, 검증, 저장 등)                                                                | 추론 실행 (실시간 예측 등)                         |
| **메모리 점유율 구성** | - 모델 파라미터<br>- 옵티마이저 상태 (Adam 등)<br>- Gradients<br>- Batch Input<br>- Activation 저장 | - 모델 파라미터<br>- Batch Input<br>- 중간 계산 결과 |
| **필요 메모리 크기**  | 매우 큼 (모델 크기의 3\~5배 이상 필요)                                                           | 상대적으로 작음 (모델 크기 수준)                      |
| **메모리 최적화 요소** | Mixed Precision, Gradient Checkpointing                                             | TensorRT, 모델 Quantization (FP16/INT8 등)  |
| **스케일링 방식**    | Multi-GPU / Multi-node 병렬 학습                                                        | 다수의 추론 요청 처리 (Batching, 분산 추론)           |
| **예시**         | GPT-4, BERT 학습 시 80GB 이상 필요 가능                                                      | 같은 모델로 수천 건 추론 시 16GB\~40GB로도 가능         |



# GP Sizing 고려 사항
| 구분                    | 항목                  | 설명                                                                                 |
| --------------------- | ------------------- | ---------------------------------------------------------------------------------- |
|  **기본 고려 항목**       | **LLM Model**       | 모델 크기(ex) 7B, 13B, 65B 등)에 따라 GPU 메모리와 연산량이 크게 달라짐                                  |
|                       | **Batch Size**      | 클수록 학습 속도↑ 하지만 GPU 메모리 소모도 ↑                                                       |
|                       | **Optimizer Type**  | ex) Adam, LAMB 등 – 옵티마이저 상태가 추가 메모리 사용 (최대 2\~3배)                                   |
|                       | **Checkpoint Save** | 주기적으로 모델 상태 저장 → I/O 및 메모리/디스크 요구량 증가                                              |
|  **최적화 적용 시 고려 항목** | **LoRA Rank**       | 파라미터 효율 최적화 기법 사용 시, Rank 설정이 GPU 메모리 요구량에 직접 영향<br>ex) 낮은 Rank → 적은 메모리 사용 & 빠른 훈련 |

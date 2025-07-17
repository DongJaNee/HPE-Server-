<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a4f2f497-0462-48a2-82a4-69de4087d366" /># 신뢰할 수 있는 AI 와 HPC 인프라 구축
- 서버,스토리지,네트워킹 중요
- AI사용함으로서, 점진적으로 global GDP가 상승하고있다.

--- 


## "How large could the compute demand for Gen AI?"
| AI 분야                             | 2024년 연산량     | 2030년 예측 연산량                  | 증가 비율    |
| --------------------------------- | ------------- | ----------------------------- | -------- |
| **Chatbot** (예: ChatGPT)          | 10 EFLOP/s    | 200 EFLOP/s                   | 20배      |
| **Enterprise AI** (예: RAG, 사기 탐지) | 15 EFLOP/s    | 440 EFLOP/s                   | 29배      |
| **Agentic AI** (예: 자동 워크플로우)      | \~200 EFLOP/s | 14 ZFLOP/s (14,000 EFLOP/s)   | 70배      |
| **Physical AI** (예: 로봇, FSD 등)    | N/A (현재 없음)   | 최대 YFLOP/s (1,000 ZFLOP/s 이상) | 1000배 이상 |


- AI의 연산 수요는 향후 5년간 폭발적으로 증가할 것으로 예상
- 특히 Agentic AI와 Physical AI는 현재보다 수십~수천 배 이상의 연산을 요구
- 이 전망은 데이터센터, 서버, GPU 인프라 확대 필요성을 강조하며 HPE와 NVIDIA의 기술 및 인프라 제품이 이에 대응할 수 있다는 메시지를 전달하려는 목적

# NVIDIA에서 소개한 AI
llama3.1 : generation에 특화  
nemoretriever : 차트에 특화 
amdocs가 만든 solution -> 통신요금고지서 분석 -------> AI를 학습시켜야함
BlackRock's Aladdin -> 

※ 참고자료 : https://build.nvidia.com/blueprints

# Agentic AI 위한 최적의 시스템 
- NVidia 모델 1개를  HPC Cluster로 구축시킨 뒤 q8n로 각각 필요한  할당해서 사용

# HPE ompute XD690 Introduce
Enabling service providers and ambitious AI model builders with
**Optimise performance**
- Latest NVIDIA Blackwell Ultra HGX B300 GPUs
- 2x Intel Xeon 6 processors
- 50% higher FP4 performance and 2X GPU-CPU bandwidth than prior gen
- 10U, air-cooled
- XDR InfiniBand and Spectrum-X Ethernet support
- HPE Performance Cluster Manager (HPCM)

# NVIDIA GB200 NVL72 & GB300 NVL72 by HPE
- NVIDIA의 Grace + Blackwell 기반 AI 슈퍼컴퓨터
- 72 GPU 구성
- 고속 NVLink 5
- 수냉식 냉각

# AI is reshaping industries, economies, and the future of innovation
- Enabling ground-breaking discoveries
- Boosting economic competitiveness
- Unlocking efficiencies
- Driving new business models



